<?xml version="1.0"?>
<?xml-stylesheet type="text/xsl" href="../entries2html.xsl" ?>
<entry type="method" name="strictEqual">
	<title>strictEqual()</title>
	<signature>
		<argument name="actual" type="Object">
			<desc>Expression being tested</desc>
		</argument>
		<argument name="expected" type="Object">
			<desc>Known comparison value</desc>
		</argument>
		<argument name="message" type="String" optional="true">
			<desc>A short description of the assertion</desc>
		</argument>
	</signature>
	<desc>
		A strict type and value comparison.
	</desc>
	<longdesc>
		<p>The <code>strictEqual()</code> assertion provides the most rigid comparison of type and value with the strict equality operator (<code>===</code>).</p>
		<p><a href="/equal/"><code>equal()</code></a> can be used to test non-strict equality.</p>
		<p><a href="/notStrictEqual/"><code>notStrictEqual()</code></a> can be used to explicitly test strict inequality.</p>
	</longdesc>
	<example>
		<desc>Compare the value of two primitives, having the same value and type.</desc>
<code><![CDATA[
QUnit.test( "strictEqual test", function( assert ) {
	assert.strictEqual( 1, 1, "1 and 1 have the same value and type" );
});
]]></code>
	</example>

	<category slug="assert"/>
</entry>
