###Query 1: CREATE TABLE BOOKSHELVES (id SERIAL PRIMARY KEY, name VARCHAR(255));

Creates a 2nd table named 'bookshelves' in books_app.

###Query 2: INSERT INTO bookshelves(name) SELECT DISTINCT bookshelf FROM books;

Inserts every unique entry found in the bookshelf fields of books into the bookshelves field created in Query 1.

###Query 3: ALTER TABLE books ADD COLUMN bookshelf_id INT;

Adds a column named bookshelf_id to books.

###Query 4: UPDATE books SET bookshelf_id=shelf.id FROM (SELECT * FROM bookshelves) AS shelf WHERE books.bookshelf = shelf.name;

Syncs the row of books with the name matching the bookshelf tag and assigns the id to bookshelf_id.  

###Query 5: ALTER TABLE books DROP COLUMN bookshelf;

Deletes teh bookshelf column.

###Query 6: ALTER TABLE books ADD CONSTRAINT fk_bookshelves FOREIGN KEY (bookshelf_id) REFERENCES bookshelves(id);

Adds Foreign Key references to bookshelves(id).