This is a partial port of [Fuse.js](https://github.com/krisk/Fuse/) for use within my personal projects.

Licensed under [Apache License 2.0](./LICENSE), similar to the original project.

Usage :
```csharp
public class Book
{
    public string Title;
    public string AuthorFirstName;
    public string AuthorLastName;
}

Book[] books =
{
    new() { Title = "Old Mans War", AuthorFirstName = "John", AuthorLastName = "Scalzi" },
    new() { Title = "The Lock Artist", AuthorFirstName = "Steve", AuthorLastName = "Hamilton" },
};

var fuse = new Fuse<Book>(books, false,
    new StringFuseField<Book>(book => book.Title),
    new StringFuseField<Book>(book => book.AuthorFirstName),
    new StringFuseField<Book>(book => book.AuthorLastName)
);

var result = fuse.Search(query);
```