## Storm Creative Media in-house PHP Styleguide

---

To keep code tidy, maintainable and a little less ugly we need to adhere to a unified Styleguide across the team. This document will cover
the techniques and preferred practise by Storm Creative development team.

Consistency is key, a common formatting must be followed at all times. This is achieved through consistent syntax, commenting and naming conventions.

---

### Documenting Code

Documenting your code is a must, this is done through applying comments to relevent parts of your code. You should aim for your code to speak for itself, but 
wherever you've had to do something a bit funky that you won't remember later, make an inline comment.

When documenting an arguments, properties type you will need to state any of the following:
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


#### Commenting Setting

#### Inline comments



