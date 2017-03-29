<?xml version="1.0"?>
<?xml-stylesheet type="text/xsl" href="../entries2html.xsl" ?>
<entry type="method" name="throws">
	<title>throws()</title>
	<signature>
		<argument name="block" type="Function">
			<desc>Function to execute</desc>
		</argument>
		<argument name="expected" type="Object" optional="true">
			<desc>Error Object (instance), Error Function (constructor), a RegExp that matches (or partially matches) the String representation, or a callback Function that must return <code>true</code> to pass the assertion check.</desc>
		</argument>
		<argument name="message" type="String" optional="true">
			<desc>A short description of the assertion</desc>
		</argument>
	</signature>
	<desc>
		Test if a callback throws an exception, and optionally compare the thrown error.
	</desc>
	<longdesc>
		<p>When testing code that is expected to throw an exception based on a specific set of circumstances, use <code>assert.throws()</code> to catch the error object for testing and comparison.</p>
		<p class="note">In very few environments, like Closure Compiler, <code>throws</code> is considered a reserved word and will cause an error. For that case, an alias is bundled called <code>raises</code>. It has the same signature and behaviour, just a different name.</p>
	</longdesc>
	<example height="250">
		<desc>Assert the correct error message is received for a custom error object.</desc>
<code><![CDATA[
QUnit.test( "throws", function( assert ) {

	function CustomError( message ) {
		this.message = message;
	}

	CustomError.prototype.toString = function() {
		return this.message;
	};

	assert.throws(
		function() {
			throw "error"
		},
		"throws with just a message, not using the 'expected' argument"
	);

	assert.throws(
		function() {
			throw new CustomError("some error description");
		},
		/description/,
		"raised error message contains 'description'"
	);

	assert.throws(
		function() {
			throw new CustomError();
		},
		CustomError,
		"raised error is an instance of CustomError"
	);

	assert.throws(
		function() {
			throw new CustomError("some error description");
		},
		new CustomError("some error description"),
		"raised error instance matches the CustomError instance"
	);

	assert.throws(
		function() {
			throw new CustomError("some error description");
		},
		function( err ) {
			return err.toString() === "some error description";
		},
		"raised error instance satisfies the callback function"
	);
});
]]></code>
	</example>

	<category slug="assert"/>
</entry>
