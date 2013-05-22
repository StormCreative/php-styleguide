## Storm Creative Media in-house PHP Styleguide

---

To keep code tidy, maintainable and a little less ugly we need to adhere to a unified Styleguide across the team. This document will cover
the techniques and preferred practise by Storm Creative development team.

Consistency is key, a common formatting must be followed at all times. This is achieved through consistent syntax, commenting and naming conventions.

---

### Documenting Code

Documenting your code is a must, this is done through applying comments to relevent parts of your code. You should aim for your code to speak for itself, but 
wherever you've had to do something a bit funky that you won't remember later, make an inline comment.

When documenting any arguments, properties type you will need to state any of the following:
<ul>
    <li>string</li>
    <li>array</li>
    <li>bool</li>
    <li>object</li>
    <li>optional</li>
</ul>

#### Documenting Methods

We follow a PHPDoc Styleguide of PHP. When documenting your class methods/functions you will do so in the following manner:
<pre>
<code>
        /**
         *  Description
         *
         *  @access private/protected
         *
         *  @param parameter type
         *  @return return type
         */
</code>
</pre>

With a real world example, the comment will look like the below with a real method:
<pre>
<code>
        /**
         *  This is an example method to illustrate the comments
         *
         *  @access protected
         *
         *  @param string $name
         *  @param optional string $name
         *  @return bool
         */
         protected function example_method( $name, $email="" )
         {
            $output = false;

            if( $name == $email ) {
                $output = true;
            }

            return $output;
         }
</code>
</pre>

#### Documenting Class Properties
To make it clear what a classes properties are used for - it's useful to document them. The style of documenting a property is as such:

<pre>
    <code>
        /**
         * This holds the users name
         *
         * @var string
         */
         public $name;
    </code>
</pre>


#### Commenting System Settings
If you make a change to a Frameworks structure or are writing your own appliction you'll find you need document a file some settings or constants, global variables.
To make the structure tidy you will document these types of settings like below:

<pre>
    <code>
        /*
        |----------------------------------------------------------------
        | Application Global Settings
        |----------------------------------------------------------------
        |
        | This is an example of explaining a specific section of settings
        |
        | This could be used to explain one setting if it does not relate
        | to any others or to explain a block
        |
        */

        //---------------------------------------------------------------
        // This is to explain a setting within a block described above
        //---------------------------------------------------------------
        $site = '/example/';

    </code>
</pre>

#### Inline comments

Only use inline comments when something warrants an explanation, if the code used a crazy technique that only you would ever understand
then use inline comment. However, only use these when it's absolutely neccessary, do not bombard your code with them.

An example of BAD inline comments:

<pre>
    <code>
        function example()
        {
            // This variable is defaulted
            $default = true;

            // Checking whether default is true
            if( $default ) {
                // Set the name to be a new name
                $name = 'A new name';
            } else {
                // Otherwise we set the name differently
                $name = 'Different name';
            }

            // return the new name
            return $name;
        }
    </code>
</pre>

The reason the above is a bad example is becaused the comments get in the way of the code - code should speak for itself.

An example of acceptable inline comments:

<pre>
    <code>
        function example( $array )
        {
            for( $i=0; $i=count($array); $i++ ) {

                if( $i==1 ) {
                    // Unset previous instance as no longer needed to match
                    unset( $i-1 );
                    $array[$i] = 'doing something';
                }
            }
            return $array;
        }
    </code>
</pre>

The above is a good example as it explains why the developer is unsetting an instance - as it is not immediately clear why you would do something like this ( this is only an example ) so it warrants an explanation.

### Naming Conventions

#### Variables, methods, functions

Variables, methods and functions all follow the 'Snake' naming convention and *not* Camel Case.

An example of Camel Case is:

<pre>
    <code>
        function thisIsCamelCase();
    </code>
</pre>

However we use Snake, as it's easier to read and looks tidier - see for yourself:

<pre>
    <code>
        function this_is_camel_case();
    </code>
</pre>

#### Classes

Classes must start with a capital letter - and when instantiated a class you must refer to it with a capital letter. This keeps the code base tidy and formal.

Below is expected and acceptable class definition: 

<pre>
    <code>
        class Example extends Base_example {

            public function example_method()
            {

            }

        }

        $example = new Example();
    </code>
</pre>

### Code Structure

#### Parentheses

The position of parentheses vary between whether they are wrapping a class, method or statements.

The below class demonstrates how all types of parentheses will be used. Take note of how a Class uses the braces, the methods, and the statements within a method. This is how they should be used anywhere within a code base:

<pre>
    <code>
        class Example extends Base_example {

            public function example_method()
            {
                $array = array( 1,2,3 );

                if( $something == true ) {
                    foreach( $array as $item ) {
                        $string .= $item;
                    }
                }

                return $string;
            }

        }
    </code>
</pre>

As you will notice, when using an IF or a Foreach or anything other than a Class or Method, the curly braces go after *not* underneath.







