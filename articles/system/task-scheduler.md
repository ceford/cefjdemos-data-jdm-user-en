<!-- Filename: J4.x:Task_Scheduler / Display title: Task Scheduler -->

## Limit Task to CLI only

To implement a task, which is executed via CLI only add the following
code to the task XML:

```xml
<fieldset name="aside">
	<field name="cli_exclusive" type="hidden" default="1" />
</fieldset>
```

The fieldset must be a direct child of the form

```xml
<form>
	<fieldset name="aside">
		<field name="cli_exclusive" type="hidden" default="1" />
	</fieldset>
...
