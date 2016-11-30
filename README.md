# my-css-cheat-sheet

Boilerplate for creating a CSS cheat sheet

## Purpose

- What you should end up with is a styled page that you can reference
  quickly for looking up some CSS

## Instructions

- Since you are already an HTML master, I've already helped you out by creating
  some news content.

- You should take note of what you are getting for free.
  - A couple sections, each with a couple of articles. These are new HTML5
    elements that add more context to the content, but they work the same
    as any other element.
  - In other words, I am giving you a document with content and structure.
    - If you want to read more:
      - Section: The section element represents a generic section of a
        document or application. A section, in this context, is a thematic
        grouping of content, typically with a heading.
      - Article: The article element represents a self-contained composition
        in a document, page, application, or site and that is, in principle,
        independently distributable or reusable, e.g. in syndication. This
        could be a forum post, a magazine or newspaper article, a blog entry,
        a user-submitted comment, an interactive widget or gadget, or any
        other independent item of content.

- Load this page in a browser
  - Note that the headers should look a little different than the
    paragraph text.
  - This is not because headers work differently than paragraphs. This is
    because browser come with built-in style called User Agent Styles.
  - Inspect each of the elements using Chrome and note in the Styles tab
    that styles being applied are coming from the "user agent stylesheet".
  - CSS Resets "unstyle" the User Agent Styles so developers can normalize
    rendering behavior as much as possible across browsers

- In the index.html, differentiate the "Weather" header from the
  "Celebrity News" header by making the "Weather" header red and the
  "Celebrity News" header blue. They should look like the below. Commit
  your changes.

    <h1 style="color: red;">Weather</h1>
    <h1 style="color: blue;">Celebrity News</h1>

  - These are inline styles because they are embedded in the HTML

- Inline styles can be convenient because they are embedded into the element
  they are styling, but they can be cumbersome for the same reason, i.e.,
  the embedded styling does not draw a clear separation of responsibilities
  between document structure and content and document style.
- It would be nice to have a "styling section" and a "content section," but
  since there are two elements of the same type we are trying to style, we
  need a way to differentiate them.
  - Remove the inline styles and give both headers an ID. They should look
    like this:

      <h1 id="weather">Weather</h1>
      <h1 id="celebrity-news">Celebrity News</h1>

  - Move the styles to the head by creating a style block in the head that
    looks like this:

      <style>
        #weather {
          color: red;
        }
        #celebrity-news {
          color: blue;
        }
      </style>

  - Quite a few things to note here:
    - The style block is going in the head because this is data for the
      browser, not content for the user
    - The syntax in the style block is CSS
    - The CSS inside the curly braces should look the exact same as what was
      used in the inline styles
    - The CSS outside the curly braces is used to select a target on which
      to apply the styles
    - Because a link needs to exist between the CSS and HTML, the HTML
      had to be supplemented with more information, IDs in this case
    - Because IDs are used here, the hashtag should look familiar to the anchor
      links that were created in the HTML cheat sheet

  - Refresh the page. It should look the same. Commit your changes.

- Again, it would be nice to have more separation of concerns between the
  document structure and content and the document style.
  - Create a new file called style.css
  - Take the CSS between in the style tag and cut/paste it into the style.css
    file. The style.css file should now look like what was between the style
    tags.
  - Remove the style elements from the head and replace it with this:

    <link rel="stylesheet" type="text/css" href="style.css">

  - The stylesheet has now been separated from the document. This offers
    many benefits on top of separation of concerns.
  - Refresh the page. It should look the same. Commit your changes.

- Now take a look at the stylesheet...
  - The "CSS outside the curly braces" is the CSS selector because it
    selects the elements on which the styles should apply.
  - IDs are the most specific selectors, and you've already created
    these types of styles
  - Underline all headers by using an element selector to apply the
    text-decoration property to all h1 elements:

      h1 {
        text-decoration: underline;
      }

  - Your headers should now be underlined. Commit your changes.
  - Now we would like to highlight weather articles, however styles
    can't be applied to all article elements because there are
    non-weather related articles. IDs could be applied to each article,
    but this would be tedious to maintain because we would need an ID
    for every future weather article as well.
    - First, add a "weather-article" class to all weather related articles
    - They should look like this:

      <article class="weather-article">...</article>

    - Now that the HTML has been supplemented with hooks to target the
      elements we want, add a class selector to apply a sans-serif font:

      .weather-article {
        font-family: serif;
      }

    - Refresh the page. All the weather articles should have a different
      font. Commit your changes.

  - Now we would like to differentiate the breaking news weather articles
    from the normal weather articles. Since we know the articles are 
    descendants of the section with id weather, target these elements to
    make the font size 8px.

      #weather article {
        font-size: 8px;
      }

    - Refresh the page. The weather articles should be different than the
      breaking news weather artiles.

  - direct descendants can be targeted like this:

      ul > li {
        color: blue;
      }

  - multiple elements can be targeted like this:

      a, div.something, .otherthing {
        /*
        this targets all a tags, div tags with class "something",
        and all elements with class "otherthing"

        this also shows you how to make CSS comment
        */
        color: red;
      }

- Some attributes you should try:
  - color
  - font-family
  - font-size
  - background-color
  - background-image
  - background-repeat
  - width
  - height

- Sometimes you need units for properties like width and height
- Some units you might use:
  - percent (%)
  - pixels (px)
  - proportional (em)

- When using colors
  - You could use keywords: red, blue, orange
  - You could use RGB (red, green blue) values: rgb(10, 160, 30)
  - RGBA values (like RGB, but takes 4 values... 4th is for opacity)

- When styling text:
  - text-align
  - text-transform
  - line-height

- When styling lists:
  - list-style-type
  - list-style-image
  - list-style

- Try some of these out. Commit and save your changes.
