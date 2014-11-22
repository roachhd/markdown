# GitHub Flavored Markdown - User Documentation

[Source](https://help.github.com/articles/github-flavored-markdown/ "Permalink to GitHub Flavored Markdown - User Documentation")
GitHub uses "GitHub Flavored Markdown," or GFM, across the site--in issues, comments, and pull requests. It differs from standard Markdown (SM) in a few significant ways, and adds some additional functionality.

If you'd like to know more about features that are available in issues, comments, and pull request descriptions, such as task lists, read [Writing on GitHub][2].

###  Differences from traditional Markdown

####  Multiple underscores in words

"Normal" Markdown transforms underscores (`_`) into italics, such that `wow_great_stuff` becomes wow_great_stuff.

It is not reasonable to italicize just _part_ of a word, especially when you're dealing with code and names often appear with multiple underscores. Therefore, GFM ignores underscores in words, like this:

* wow_great_stuff
* do_this_and_do_that_and_another_thing.

####  URL autolinking

GFM will autolink standard URLs, so if you want to link to a URL (instead of setting link text), you can simply enter the URL and it will be turned into a link to that URL.


    http://example.com


becomes



####  Strikethrough

GFM adds syntax to create strikethrough text, which is missing from standard Markdown.


    ~~Mistaken text.~~


becomes

Mistaken text.

####  Fenced code blocks

Standard Markdown converts text with four spaces at the beginning of each line into a code block; GFM also supports fenced blocks. Just wrap your code in ````` (as shown below) and you won't need to indent it by four spaces. Note that although fenced code blocks don't have to be preceded by a blank line—unlike indented code blocks—we recommend placing a blank line before them to make the raw Markdown easier to read.


    Here's an example:

    ```
    function test() {
      console.log("notice the blank line before this function?");
    }
    ```


Keep in mind that, within lists, you must indent non-fenced code blocks _eight_ spaces to render them properly.

####  Syntax highlighting

Code blocks can be taken a step further by adding syntax highlighting. In your fenced block, add an optional language identifier and we'll run it through syntax highlighting. For example, to syntax highlight Ruby code:


    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```


We use [Linguist][3] to perform language detection and syntax highlighting. You can find out which keywords are valid by perusing [the languages YAML file][4].

####  Tables

You can create tables by assembling a list of words and dividing them with hyphens `-` (for the first row), and then separating each column with a pipe `|`:



    First Header  | Second Header
    ------------- | -------------
    Content Cell  | Content Cell
    Content Cell  | Content Cell




For aesthetic purposes, you can also add extra pipes on the ends:



    | First Header  | Second Header |
    | ------------- | ------------- |
    | Content Cell  | Content Cell  |
    | Content Cell  | Content Cell  |




Note that the dashes at the top don't need to match the length of the header text exactly:



    | Name | Description          |
    | ------------- | ----------- |
    | Help      | Display the help window.|
    | Close     | Closes a window     |




You can also include inline Markdown such as links, bold, italics, or strikethrough:



    | Name | Description          |
    | ------------- | ----------- |
    | Help      | ~~Display the~~ help window.|
    | Close     | _Closes_ a window     |




Finally, by including colons `:` within the header row, you can define text to be left-aligned, right-aligned, or center-aligned:



    | Left-Aligned  | Center Aligned  | Right Aligned |
    | :------------ |:---------------:| -----:|
    | col 3 is      | some wordy text | $1600 |
    | col 2 is      | centered        |   $12 |
    | zebra stripes | are neat        |    $1 |




A colon on the **left-most** side indicates a left-aligned column; a colon on the **right-most** side indicates a right-aligned column; a colon on **both** sides indicates a center-aligned column.

###  HTML

You can use a subset of HTML within your READMEs, issues, and pull requests.

A full list of our supported tags and attributes can be found in [the README for github/markup][5].

###  Further reading

[1]: https://help.github.com/articles/markdown-basics
[2]: https://help.github.com/articles/writing-on-github
[3]: https://github.com/github/linguist
[4]: https://github.com/github/linguist/blob/master/lib/linguist/languages.yml
[5]: https://github.com/github/markup/tree/master#html-sanitization
