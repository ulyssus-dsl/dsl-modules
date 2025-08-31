# DSL QuillForge

The DSL QuillForge is a module that allows for easy management of books and documents in the [Dark & Shattered Lands](http://www.dsl-mud.org) Mud. This module makes it possible to easily design and write copies of books and documents using Mudlet scripts that manage the configuration of the books and documents. This module also allows the books and documents to be viewed in Mudlet directly without a copy of the book, allows for easy reading of existing copies of the books, and searching for copies of the books in containers such as public pits. Existing books and documents in the game can also be cloned into a QuillForge script for easy duplication of them.

DSL QuillForge was written and tested on Mudlet 4.19.1.

## Installation

To install the DSL QuillForge module, download [DSL-QuillForge.xml](DSL-QuillForge.xml) and in Mudlet go to Toolbox -> Module Manager -> Install to install the module.

## Usage

Once the module has been installed, type `quill` to begin using it.

## Features

The QuillForge module offers the following features.

### Writing, Reading, & Viewing Books & Documents

The QuillForge makes writing books and documents easy by using Mudlet scripts written in lua to configure the layout of the books and documents to be written. The following is an example of a simple book script for a journal:

```lua
dsl = dsl or {}
dsl.quillforge = dsl.quillforge or {}
dsl.quillforge.books = dsl.quillforge.books or {}

dsl.quillforge.books["journal"] = {
  names = "leather journal",
  title = "a leather journal",
  pages = {
    {
      " -------------- {WSomeone's Journal{x --------------",
      " ",
      "PARAGRAPH The first paragraph of someone's journal."
    },
    {
      "The second page of the journal.",
    },
  }
}
```

With the script saved in Mudlet, and a container with a quill, ink, and small book available, the book can easily be written using the command `quill write book journal`. If changes are made to the book's script, the book can be fully rewritten using `quill rewrite book journal` or a specific page can be rewritten using `quill rewrite book journal 2`.

Along with writing books, QuillForge can read a full book or portion of a book using `quill read book journal` or `quill read book journal 2` which will read the pages and all sections of the pages based on the current characters scroll settings.

Books can also be viewed directly in Mudlet and echoed to the console without requiring a copy of the book by using `quill view book journal` or `quill view book journal 2`.

### Cloning Existing Books & Documents

QuillForge is also capable of cloning existing in game books and documents by using the command `quill clone book journal leather journal` which will take a book in inventory that has the names of 'leather journal' and will read the entire book and then copy the script for the book to your clipboard with the alias of 'journal' that when added into a new Mudlet script will allow the book to be available for writing/viewing within QuillForge.

### Searching For Books & Documents In Containers

QuillForge will also allow the full list of books and documents that show within the `quill list books` or `quill list docs` commands to be searched for in a container or a clan/kingdom pit by using the command `quill search books pit` allowing you to see which books or documents are missing from the container when keeping a container stocked with copies.
