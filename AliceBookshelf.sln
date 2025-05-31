using System;
using System.Collections.Generic;
using System.Linq;

class Book
{
    public string Title { get; set; }
    public string Author { get; set; }

    public Book(string title, string author)
    {
        Title = title;
        Author = author;
    }

    public void Display()
    {
        Console.WriteLine($"📖 \"{Title}\" by {Author}");
    }
}

class Bookshelf
{
    private List<Book> books = new List<Book>();

    public void AddBook(string title, string author)
    {
        books.Add(new Book(title, author));
        Console.WriteLine($"✅ Added \"{title}\" to Alice's bookshelf.");
    }

    public void ViewBooks()
    {
        Console.WriteLine("\n📚 Alice's Bookshelf:");
        if (books.Count == 0)
        {
            Console.WriteLine("No books yet.");
            return;
        }

        foreach (var book in books)
        {
            book.Display();
        }
    }

    public void RemoveBook(string title)
    {
        var book = books.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
        if (book != null)
        {
            books.Remove(book);
            Console.WriteLine($"❌ Removed \"{title}\" from the bookshelf.");
        }
        else
        {
            Console.WriteLine($"⚠️ Book titled \"{title}\" not found.");
        }
    }
}

class Program
{
    static void Main()
    {
        Bookshelf aliceShelf = new Bookshelf();

        while (true)
        {
            Console.WriteLine("\n=== Alice's Bookshelf Menu ===");
            Console.WriteLine("1. Add a Book");
            Console.WriteLine("2. View Books");
            Console.WriteLine("3. Remove a Book");
            Console.WriteLine("4. Exit");
            Console.Write("Select an option (1-4): ");
            string input = Console.ReadLine();

            switch (input)
            {
                case "1":
                    Console.Write("Enter book title: ");
                    string title = Console.ReadLine();
                    Console.Write("Enter author: ");
                    string author = Console.ReadLine();
                    aliceShelf.AddBook(title, author);
                    break;

                case "2":
                    aliceShelf.ViewBooks();
                    break;

                case "3":
                    Console.Write("Enter title of book to remove: ");
                    string removeTitle = Console.ReadLine();
                    aliceShelf.RemoveBook(removeTitle);
                    break;

                case "4":
                    Console.WriteLine("👋 Goodbye, Alice!");
                    return;

                default:
                    Console.WriteLine("Invalid option. Try again.");
                    break;
            }
        }
    }
}
