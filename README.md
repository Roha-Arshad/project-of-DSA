# project-of-DSA
CLASS BOOK:
package LibraryManagmentSystem;

public class Book {

	 String title;
	    String author;
	    boolean isIssued;

	    public Book(String title, String author) {
	        this.title = title;
	        this.author = author;
	        this.isIssued = false; // Initially, the book is available
	    }

	    public void issueBook() {
	        isIssued = true;
	    }

	    public void returnBook() {
	        isIssued = false;
	    }

	    public boolean isAvailable() {
	    	return !isIssued;
	    }

	    @Override
	    public String toString() {
	        return "Title: " + title + ", Author: " + author + ", Available: " + (isIssued ? "No" : "Yes");
	    }
	
	    }


CLASS LIBRARY:
package LibraryManagmentSystem;

      public interface LibraryOperations {

	    void addBook(Book book);
	    void issueBook(String title);
	    void returnBook(String title);
	    void viewAvailableBooks();
	    
       }


public class Library implements LibraryOperations{

	
	    class Node {
	        Book book;
	        Node next;

	        public Node(Book book) {
	            this.book = book;
	            this.next = null;
	        }
	    }

	    private Node head;

	    public Library() {
	        head = null;
	    }

	    @Override
	    public void addBook(Book book) {
	        Node newNode = new Node(book);
	        if (head == null) {
	            head = newNode;
	        } else {
	            Node temp = head;
	            while (temp.next != null) {
	                temp = temp.next;
	            }
	            temp.next = newNode;
	        }
	    }

	    @Override
	    public void issueBook(String title) {
	        Node current = head;
	        while (current != null) {
	            if (current.book.title.equals(title) &&current.book.isAvailable()) {
	                current.book.issueBook();
	                System.out.println("Book issued: " + title);
	                return;
	            }
	            current = current.next;
	        }
	        System.out.println("Book not available or already issued.");
	    }

	    @Override
	    public void returnBook(String title) {
	        Node current = head;
	        while (current != null) {
	            if (current.book.title.equals(title) && !current.book.isAvailable()) {
	                current.book.returnBook();
	                System.out.println("Book returned: " + title);
	                return;
	            }
	            current = current.next;
	        }
	        System.out.println("This book was not issued.");
	    }

	    @Override
	    public void viewAvailableBooks() {
	        Node current = head;
	        System.out.println("Available Books:");
	        boolean found = false;
	        while (current != null) {
	            if (current.book.isAvailable()) {
	                System.out.println(current.book);
	                found = true;
	            }
	            current = current.next;
	        }
	        if (!found) {
	            System.out.println("No books are available.");
	        }
	    }

	    public static void main(String[] args) {
	        Library library = new Library();
	        
	        // Add books to the library
	        library.addBook(new Book("Harry Potter", "J.K. Rowling"));
	        library.addBook(new Book("The Hobbit", "J.R.R. Tolkien"));
	        library.addBook(new Book("The Great Gatsby", "F. Scott Fitzgerald"));
	        System.out.println();
	        // View available books
	        library.viewAvailableBooks();
	        System.out.println();
	        // Issue a book
	        library.issueBook("Harry Potter");
	        System.out.println();
	        // Try to issue the same book again
	        library.issueBook("Harry Potter");
	        System.out.println();
	        // Return a book
	        library.returnBook("Harry Potter");
	        System.out.println();
	        // View available books after return
	        library.viewAvailableBooks();
	    }
	}CLASS BOOK:
package LibraryManagmentSystem;

public class Book {

	 String title;
	    String author;
	    boolean isIssued;

	    public Book(String title, String author) {
	        this.title = title;
	        this.author = author;
	        this.isIssued = false; // Initially, the book is available
	    }

	    public void issueBook() {
	        isIssued = true;
	    }

	    public void returnBook() {
	        isIssued = false;
	    }

	    public boolean isAvailable() {
	    	return !isIssued;
	    }

	    @Override
	    public String toString() {
	        return "Title: " + title + ", Author: " + author + ", Available: " + (isIssued ? "No" : "Yes");
	    }
	
	    }


CLASS LIBRARY:
package LibraryManagmentSystem;

      public interface LibraryOperations {

	    void addBook(Book book);
	    void issueBook(String title);
	    void returnBook(String title);
	    void viewAvailableBooks();
	    
       }


public class Library implements LibraryOperations{

	
	    class Node {
	        Book book;
	        Node next;

	        public Node(Book book) {
	            this.book = book;
	            this.next = null;
	        }
	    }

	    private Node head;

	    public Library() {
	        head = null;
	    }

	    @Override
	    public void addBook(Book book) {
	        Node newNode = new Node(book);
	        if (head == null) {
	            head = newNode;
	        } else {
	            Node temp = head;
	            while (temp.next != null) {
	                temp = temp.next;
	            }
	            temp.next = newNode;
	        }
	    }

	    @Override
	    public void issueBook(String title) {
	        Node current = head;
	        while (current != null) {
	            if (current.book.title.equals(title) &&current.book.isAvailable()) {
	                current.book.issueBook();
	                System.out.println("Book issued: " + title);
	                return;
	            }
	            current = current.next;
	        }
	        System.out.println("Book not available or already issued.");
	    }

	    @Override
	    public void returnBook(String title) {
	        Node current = head;
	        while (current != null) {
	            if (current.book.title.equals(title) && !current.book.isAvailable()) {
	                current.book.returnBook();
	                System.out.println("Book returned: " + title);
	                return;
	            }
	            current = current.next;
	        }
	        System.out.println("This book was not issued.");
	    }

	    @Override
	    public void viewAvailableBooks() {
	        Node current = head;
	        System.out.println("Available Books:");
	        boolean found = false;
	        while (current != null) {
	            if (current.book.isAvailable()) {
	                System.out.println(current.book);
	                found = true;
	            }
	            current = current.next;
	        }
	        if (!found) {
	            System.out.println("No books are available.");
	        }
	    }

	    public static void main(String[] args) {
	        Library library = new Library();
	        
	        // Add books to the library
	        library.addBook(new Book("Harry Potter", "J.K. Rowling"));
	        library.addBook(new Book("The Hobbit", "J.R.R. Tolkien"));
	        library.addBook(new Book("The Great Gatsby", "F. Scott Fitzgerald"));
	        System.out.println();
	        // View available books
	        library.viewAvailableBooks();
	        System.out.println();
	        // Issue a book
	        library.issueBook("Harry Potter");
	        System.out.println();
	        // Try to issue the same book again
	        library.issueBook("Harry Potter");
	        System.out.println();
	        // Return a book
	        library.returnBook("Harry Potter");
	        System.out.println();
	        // View available books after return
	        library.viewAvailableBooks();
	    }
	}





