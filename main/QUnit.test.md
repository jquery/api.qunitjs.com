<?xml version="1.0"?>
<?xml-stylesheet type="text/xsl" href="../entries2html.xsl" ?>
<entry type="method" name="QUnit.test">
	<title>QUnit.test()</title>
	<signature>
		<argument name="name" type="String">
			<desc>Title of unit being tested</desc>
		</argument>
		<argument name="callback">
			<desc>Function to close over assertions</desc>
			<type name="Function">
				<argument name="assert" type="Assert"></argument>
			</type>
		</argument>
	</signature>
	<desc>
		Add a test to run.
	</desc>
	<longdesc>
		<p>Add a test to run using <code>QUnit.test()</code>.</p>
		<p>The <a href="/QUnit.assert/"><code>assert</code></a> argument to the callback contains all of QUnit's <a href="/category/assert/">assertion methods</a>. Use this argument to call your test assertions.</p>
		<p><code>QUnit.test()</code> can automatically handle the asynchronous resolution of a Promise on your behalf if you return a <code>then</code>able Promise as the result of your callback function.</p>
	</longdesc>
	<example height="250">
		<desc>A practical example, using the assert argument and no globals.</desc>
<code><![CDATA[
QUnit.test( "a test", function( assert ) {

	function square( x ) {
		return x * x;
	}

	var result = square( 2 );

	assert.equal( result, 4, "square(2) equals 4" );
});
]]></code>
	</example>
	<example height="250">
		<desc>An example of handling an asynchronous <code>then</code>able Promise result. This example uses an <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise">ES6 Promise</a> interface that is fulfilled after waiting 500ms.</desc>
<code><![CDATA[
QUnit.test( "a Promise-returning test", function( assert ) {
	assert.expect( 0 );

	var thenable = new Promise(function( resolve, reject ) {
		setTimeout(function() {
			resolve( "result" );
		}, 500 );
	});
	return thenable;
});
]]></code>
	</example>

	<category slug="test"/>
	<category slug="async-control"/>
</entry>
