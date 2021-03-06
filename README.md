# Phonetic
Generates unique, pronounceable names, random and seedable

## Installation
In your project folder, type:

	npm install phonetic

## Usage
Just require it...

	var phonetic = require('phonetic');

Need a name?

	phonetic.generate();
	// "Stratulis"
	phonetic.generate();
	// "Quibapop"

Need a shorter name?

	phonetic.generate({ syllables: 2 });
	// "Neelam"

Need to generate the same name based on some user info?

	phonetic.generate({ seed: '127.0.0.1' })
	// "Pokenoop"
	phonetic.generate({ seed: '127.0.0.1' })
    // "Pokenoop"

## Details
Phonetic generates a randomized, pronounceable word.  Use it to assign
pronounceable hostnames to your server cluster so you don't have to refer to
machines by random letters or numbers, or use it to suggest a unique username
to your site's visitors.  Keep the name the same every time by seeding it with
a unique cookie, or maybe the user's IP + user agent.

Words are generated by transforming the seed using a series of MD5 hashes and
calculations that make it impossible for users to game the system and coerce
out a chosen word.  The process is synchronous, but takes mere nanoseconds.

Generated words have an English-leaning format, using phonetics that are more
common in the English language and avoiding more international sounds.  This
could be changed by packaging the phonetic sets and replacements into modules
which can be selected through the options at run time.  A hint to those who
would like to get involved with the project!

The function call looks like this:

**phonetic.generate([options])**

### Options
The following options are available:

#### syllables
*Default: 3.* The number of syllables to put in the resulting word.

#### seed
*Default: (random).* A string or number with which to seed the generator.
Using the same seed (with the same other options) will coerce the generator
into producing the same word each time.

#### phoneticSimplicity
*Default: 5.* The greater this number, the simpler the phonetics. For example,
1 might produce 'str' while 5 might produce 's' for the same syllable.  Minimum
is 1.

#### compoundSimplicity
*Default: 5.* The greater this number, the less likely the resulting word will
sound "compound", such as "ripkuth" instead of "riputh".  Minimum is 1.

#### capFirst
*Default: true.* true to capitalize the first letter of the word; all lowercase
otherwise.

## License
Phonetic is distributed under the MIT license.  See LICENSE.txt for details.

## Credits
Phonetic was created by Tom Shawver in 2013 to ease the transition from lurking
to contributing.
