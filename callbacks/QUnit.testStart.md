<?xml version="1.0"?>
<?xml-stylesheet type="text/xsl" href="../entries2html.xsl" ?>
<entry type="method" name="QUnit.testStart">
	<title>QUnit.testStart()</title>
	<signature>
		<argument name="callback">
			<desc>Callback to execute. Provides a single argument with the following properties:</desc>
			<type name="Function">
				<argument name="details" type="Object"/>
			</type>
			<property name="name" type="String">
				<desc>Name of the next test to run</desc>
			</property>
			<property name="module" type="String">
				<desc>Name of the current module</desc>
			</property>
			<property name="testId" type="String">
				<desc>Id of the next test to run</desc>
			</property>
			<property name="previousFailure" type="Boolean">
				<desc>Whether the next test failed on a previous run</desc>
			</property>
		</argument>
	</signature>
	<desc>Register a callback to fire whenever a test begins.</desc>
	<example>
		<desc>Register a callback that logs the module and name</desc>
		<code><![CDATA[
QUnit.testStart(function( details ) {
	console.log( "Now running: ", details.module, details.name );
});
]]></code>
	</example>
	<category slug="callbacks"/>
</entry>
