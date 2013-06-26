# TextRuleSetSerializer
=====================

An improved version of [Chris Eyre's Windows Workflow rule serializer](http://devrants.blog.com/2009/03/23/a-better-wf-rule-serializer/).


### Introduction
================

This is an alternative for [Windows Workflow Rules Engine](http://msdn.microsoft.com/en-us/library/dd554919.aspx)'s default serializer - WorkflowMarkUpSerializer.
This version serializes a RuleSet in a more readable XML format, making it easier to resolve version control merge conflicts.

Sample RuleSet with one rule:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<RuleSet.Text Name="ClinicalDocumentRuleSet="" ChainingBehavior="Full">
   <Rule Active="True" Description="" Name="ExpiryRule" Priority="5" ReevaluationBehavior="Always">
      <Condition>this.Expiry &lt; System.DateTime.Now</Condition>
      <ThenActions>
         <Action>System.Console.WriteLine("Firing ExpiryRule")</Action>
         <Action>this.Expiry = System.DateTime.Now.AddDays(1)</Action>
      </ThenActions>
      <ElseActions>
         <Action>System.Console.WriteLine("Document expiry date is ok")</Action>
      </ElseActions>
   </Rule>
</RuleSet.Text>
```


### Goals
=========

This project aims to:
* fix bugs encountered in the original code and
* provide an updated version for .NET 4.5.


### Credits
===========

Credits go to [Chris Eyre](http://devrants.blog.com/author/chris-19/).
