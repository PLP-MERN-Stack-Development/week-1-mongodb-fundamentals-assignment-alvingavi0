[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=19734222&assignment_repo_type=AssignmentRepo)
# MongoDB Fundamentals Assignment

This assignment focuses on learning MongoDB fundamentals including setup, CRUD operations, advanced queries, aggregation pipelines, and indexing.

## Assignment Overview

You will:
1. Set up a MongoDB database
2. Perform basic CRUD operations
3. Write advanced queries with filtering, projection, and sorting
4. Create aggregation pipelines for data analysis
5. Implement indexing for performance optimization

## Getting Started

1. Accept the GitHub Classroom assignment invitation
2. Clone your personal repository that was created by GitHub Classroom
3. Install MongoDB locally or set up a MongoDB Atlas account
4. Run the provided `insert_books.js` script to populate your database
5. Complete the tasks in the assignment document

## Files Included

- `Week1-Assignment.md`: Detailed assignment instructions
- `insert_books.js`: Script to populate your MongoDB database with sample book data

## Requirements

- Node.js (v18 or higher)
- MongoDB (local installation or Atlas account)
- MongoDB Shell (mongosh) or MongoDB Compass

## Submission

Your work will be automatically submitted when you push to your GitHub Classroom repository. Make sure to:

1. Complete all tasks in the assignment
2. Add your `queries.js` file with all required MongoDB queries
3. Include a screenshot of your MongoDB database
4. Update the README.md with your specific setup instructions

## Resources

- [MongoDB Documentation](https://docs.mongodb.com/)
- [MongoDB University](https://university.mongodb.com/)
- [MongoDB Node.js Driver](https://mongodb.github.io/node-mongodb-native/) 


# MongoDB Bookstore Project

A comprehensive MongoDB project demonstrating CRUD operations, advanced queries, aggregation pipelines, and performance optimization using a bookstore database.

## 📋 Table of Contents

- [Overview](#overview)
- [Database Structure](#database-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Project Tasks](#project-tasks)
  - [Task 1: Basic CRUD Operations](#task-1-basic-crud-operations)
  - [Task 2: Advanced Queries](#task-2-advanced-queries)
  - [Task 3: Aggregation Pipelines](#task-3-aggregation-pipelines)
  - [Task 4: Indexing & Performance](#task-4-indexing--performance)
- [Performance Optimization](#performance-optimization)
- [Using MongoDB Compass](#using-mongodb-compass)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)
- [Learning Objectives](#learning-objectives)
- [Expected Results](#expected-results)
- [Contributing](#contributing)
- [Resources](#resources)

## Overview

This project implements a bookstore management system using MongoDB, featuring:

- **Database Name:** `plp_bookstore`
- **Collection:** `books`
- **Total Documents:** 12 books
- **Genres:** 8 different genres (Fiction, Fantasy, Dystopian, Romance, etc.)

## Database Structure

### Document Schema

```javascript
{
  _id: ObjectId,
  title: String,
  author: String,
  genre: String,
  published_year: Number,
  price: Number,
  in_stock: Boolean,
  pages: Number,
  publisher: String
}
```

### Sample Document

```javascript
{
  title: "To Kill a Mockingbird",
  author: "Harper Lee",
  genre: "Fiction",
  published_year: 2011,
  price: 12.99,
  in_stock: true,
  pages: 336,
  publisher: "J. B. Lippincott & Co."
}
```

## Prerequisites

- MongoDB installed and running
- MongoDB Shell (mongosh)
- MongoDB Compass (optional but recommended)
- Basic knowledge of JavaScript and MongoDB concepts

## Getting Started

### 1. Connect to MongoDB

```bash
# Using MongoDB Shell
mongosh mongodb://localhost:27017/

# Switch to project database
use plp_bookstore
```

### 2. Insert Sample Data

```javascript
// Insert all 12 books
db.books.insertMany([
  {
    title: "To Kill a Mockingbird",
    author: "Harper Lee",
    genre: "Fiction",
    published_year: 2011,
    price: 12.99,
    in_stock: true,
    pages: 336,
    publisher: "J. B. Lippincott & Co."
  },
  {
    title: "1984",
    author: "George Orwell",
    genre: "Dystopian",
    published_year: 1949,
    price: 13.99,
    in_stock: true,
    pages: 328,
    publisher: "Secker & Warburg"
  },
  {
    title: "The Great Gatsby",
    author: "F. Scott Fitzgerald",
    genre: "Fiction",
    published_year: 1925,
    price: 10.99,
    in_stock: false,
    pages: 180,
    publisher: "Charles Scribner's Sons"
  },
  {
    title: "Pride and Prejudice",
    author: "Jane Austen",
    genre: "Romance",
    published_year: 1813,
    price: 9.99,
    in_stock: true,
    pages: 432,
    publisher: "T. Egerton"
  },
  {
    title: "The Catcher in the Rye",
    author: "J.D. Salinger",
    genre: "Fiction",
    published_year: 1951,
    price: 11.99,
    in_stock: true,
    pages: 277,
    publisher: "Little, Brown and Company"
  },
  {
    title: "Animal Farm",
    author: "George Orwell",
    genre: "Dystopian",
    published_year: 1945,
    price: 8.99,
    in_stock: true,
    pages: 112,
    publisher: "Secker & Warburg"
  },
  {
    title: "Lord of the Rings",
    author: "J.R.R. Tolkien",
    genre: "Fantasy",
    published_year: 1954,
    price: 19.99,
    in_stock: true,
    pages: 1216,
    publisher: "George Allen & Unwin"
  },
  {
    title: "The Hobbit",
    author: "J.R.R. Tolkien",
    genre: "Fantasy",
    published_year: 1937,
    price: 12.99,
    in_stock: false,
    pages: 310,
    publisher: "George Allen & Unwin"
  },
  {
    title: "Brave New World",
    author: "Aldous Huxley",
    genre: "Dystopian",
    published_year: 1932,
    price: 13.99,
    in_stock: true,
    pages: 268,
    publisher: "Chatto & Windus"
  },
  {
    title: "Jane Eyre",
    author: "Charlotte Brontë",
    genre: "Romance",
    published_year: 1847,
    price: 10.99,
    in_stock: true,
    pages: 507,
    publisher: "Smith, Elder & Co."
  },
  {
    title: "The Chronicles of Narnia",
    author: "C.S. Lewis",
    genre: "Fantasy",
    published_year: 1950,
    price: 16.99,
    in_stock: true,
    pages: 767,
    publisher: "Geoffrey Bles"
  },
  {
    title: "Fahrenheit 451",
    author: "Ray Bradbury",
    genre: "Science Fiction",
    published_year: 1953,
    price: 7.99,
    in_stock: false,
    pages: 249,
    publisher: "Ballantine Books"
  }
])
```

### 3. Verify Installation

```javascript
// Check document count
db.books.countDocuments()  // Should return 12

// View all books
db.books.find().pretty()
```

## Project Tasks

### Task 1: Basic CRUD Operations

#### Create Operations

```javascript
// Insert single book
db.books.insertOne({
  title: "New Book",
  author: "Author Name",
  genre: "Fiction",
  published_year: 2024,
  price: 15.99,
  in_stock: true,
  pages: 300,
  publisher: "Publisher Name"
})

// Insert multiple books
db.books.insertMany([
  {
    title: "Book One",
    author: "Author One",
    genre: "Mystery",
    published_year: 2023,
    price: 14.99,
    in_stock: true,
    pages: 250,
    publisher: "Mystery Press"
  },
  {
    title: "Book Two",
    author: "Author Two",
    genre: "Thriller",
    published_year: 2024,
    price: 16.99,
    in_stock: false,
    pages: 320,
    publisher: "Thriller House"
  }
])
```

#### Read Operations

```javascript
// Find all Fiction books
db.books.find({ genre: "Fiction" })

// Find books by specific author
db.books.find({ author: "George Orwell" })

// Find books published after 1950
db.books.find({ published_year: { $gt: 1950 } })

// Find books with price less than $12
db.books.find({ price: { $lt: 12 } })

// Find books in stock
db.books.find({ in_stock: true })

// Find one book by title
db.books.findOne({ title: "1984" })
```

#### Update Operations

```javascript
// Update book price
db.books.updateOne(
  { title: "The Great Gatsby" },
  { $set: { price: 15.99 } }
)

// Update multiple books
db.books.updateMany(
  { genre: "Fantasy" },
  { $inc: { price: 2 } }  // Increase price by $2
)

// Update or insert (upsert)
db.books.updateOne(
  { title: "Nonexistent Book" },
  { 
    $set: { 
      title: "Nonexistent Book",
      author: "Unknown Author",
      genre: "Mystery",
      published_year: 2024,
      price: 12.99,
      in_stock: true,
      pages: 200,
      publisher: "Unknown Publisher"
    }
  },
  { upsert: true }
)
```

#### Delete Operations

```javascript
// Delete book by title
db.books.deleteOne({ title: "Book Title" })

// Delete multiple books
db.books.deleteMany({ in_stock: false })

// Delete all books by author
db.books.deleteMany({ author: "Author Name" })
```

### Task 2: Advanced Queries

#### Multiple Conditions

```javascript
// Books in stock AND published after 2010
db.books.find({ 
  in_stock: true, 
  published_year: { $gt: 2010 } 
})

// Books with price between $10 and $15
db.books.find({
  price: { $gte: 10, $lte: 15 }
})

// Books that are Fiction OR Fantasy
db.books.find({
  $or: [
    { genre: "Fiction" },
    { genre: "Fantasy" }
  ]
})
```

#### Text Search and Regular Expressions

```javascript
// Books with titles containing "the" (case insensitive)
db.books.find({
  title: { $regex: /the/i }
})

// Authors whose names start with "J"
db.books.find({
  author: { $regex: /^J/ }
})
```

#### Array Operations

```javascript
// Find books in specific genres
db.books.find({
  genre: { $in: ["Fiction", "Fantasy", "Romance"] }
})

// Find books NOT in specific genres
db.books.find({
  genre: { $nin: ["Science Fiction", "Horror"] }
})
```

#### Projection (Specific Fields)

```javascript
// Show only title, author, price
db.books.find(
  {}, 
  { title: 1, author: 1, price: 1, _id: 0 }
)

// Exclude specific fields
db.books.find(
  {},
  { publisher: 0, pages: 0 }
)
```

#### Sorting

```javascript
// Sort by price (ascending)
db.books.find().sort({ price: 1 })

// Sort by price (descending)
db.books.find().sort({ price: -1 })

// Sort by multiple fields
db.books.find().sort({ genre: 1, price: -1 })
```

#### Pagination

```javascript
// Page 1: First 5 books
db.books.find().limit(5).skip(0)

// Page 2: Next 5 books
db.books.find().limit(5).skip(5)

// Sorted pagination
db.books.find().sort({ title: 1 }).limit(3).skip(0)
```

#### Counting and Existence

```javascript
// Count all books
db.books.countDocuments()

// Count books with specific criteria
db.books.countDocuments({ genre: "Fiction" })

// Check if field exists
db.books.find({ publisher: { $exists: true } })
```

### Task 3: Aggregation Pipelines

#### Average Price by Genre

```javascript
db.books.aggregate([
  {
    $group: {
      _id: "$genre",
      average_price: { $avg: "$price" },
      book_count: { $sum: 1 },
      total_revenue: { $sum: "$price" }
    }
  },
  { $sort: { average_price: -1 } }
])
```

#### Author with Most Books

```javascript
db.books.aggregate([
  {
    $group: {
      _id: "$author",
      book_count: { $sum: 1 },
      books: { $push: "$title" },
      total_pages: { $sum: "$pages" },
      avg_price: { $avg: "$price" }
    }
  },
  { $sort: { book_count: -1 } },
  { $limit: 5 }
])
```

#### Books by Publication Decade

```javascript
db.books.aggregate([
  {
    $addFields: {
      decade: {
        $multiply: [
          { $floor: { $divide: ["$published_year", 10] } },
          10
        ]
      }
    }
  },
  {
    $group: {
      _id: "$decade",
      book_count: { $sum: 1 },
      avg_price: { $avg: "$price" },
      books: { $push: "$title" }
    }
  },
  { $sort: { _id: 1 } }
])
```

#### Price Statistics

```javascript
db.books.aggregate([
  {
    $group: {
      _id: null,
      total_books: { $sum: 1 },
      avg_price: { $avg: "$price" },
      min_price: { $min: "$price" },
      max_price: { $max: "$price" },
      total_value: { $sum: "$price" }
    }
  }
])
```

#### Books Available vs Out of Stock

```javascript
db.books.aggregate([
  {
    $group: {
      _id: "$in_stock",
      count: { $sum: 1 },
      titles: { $push: "$title" }
    }
  },
  {
    $project: {
      _id: 0,
      status: { 
        $cond: { 
          if: "$_id", 
          then: "In Stock", 
          else: "Out of Stock" 
        }
      },
      count: 1,
      titles: 1
    }
  }
])
```

### Task 4: Indexing & Performance

#### Create Indexes

```javascript
// Single field index on title
db.books.createIndex({ title: 1 })

// Single field index on author
db.books.createIndex({ author: 1 })

// Single field index on genre
db.books.createIndex({ genre: 1 })

// Compound index on author and published_year
db.books.createIndex({ author: 1, published_year: 1 })

// Compound index on genre and price
db.books.createIndex({ genre: 1, price: 1 })

// Text index for search functionality
db.books.createIndex({ 
  title: "text", 
  author: "text", 
  genre: "text" 
})
```

#### Performance Testing

```javascript
// Test query performance
db.books.find({ title: "The Great Gatsby" }).explain("executionStats")

// Test compound query performance
db.books.find({ 
  author: "George Orwell", 
  published_year: { $gte: 1940 } 
}).explain("executionStats")

// Compare before and after index creation
// Look for "COLLSCAN" vs "IXSCAN" in results
```

#### Index Management

```javascript
// View all indexes
db.books.getIndexes()

// Get index statistics
db.books.getIndexStats()

// Drop specific index
db.books.dropIndex({ title: 1 })

// Drop index by name
db.books.dropIndex("author_1_published_year_1")

// Rebuild all indexes
db.books.reIndex()
```

#### Text Search with Index

```javascript
// Search across title, author, and genre
db.books.find({ $text: { $search: "orwell dystopian" } })

// Text search with score
db.books.find(
  { $text: { $search: "tolkien fantasy" } },
  { score: { $meta: "textScore" } }
).sort({ score: { $meta: "textScore" } })
```

## Performance Optimization

### Index Strategy

- **Title Index:** Fast book lookups by title
- **Author Index:** Quick author-based queries
- **Genre Index:** Efficient genre filtering
- **Author + Year Compound Index:** Optimized author queries with date filtering
- **Text Index:** Full-text search capabilities

### Query Optimization Tips

1. **Use Indexes:** Create indexes for frequently queried fields
2. **Limit Results:** Use `.limit()` to restrict result sets
3. **Project Fields:** Use projection to return only needed fields
4. **Analyze Queries:** Use `.explain()` to understand query execution
5. **Compound Indexes:** Create compound indexes for multi-field queries
6. **Avoid Regex:** Use text indexes instead of regex for text search

### Expected Performance Improvements

With proper indexing:
- **Title searches:** COLLSCAN → IXSCAN (99% improvement)
- **Author queries:** 12 documents examined → 1-2 documents examined
- **Compound queries:** Significant performance improvement
- **Text searches:** Fast full-text search capabilities

## Using MongoDB Compass

### Connection Details

- **Connection String:** `mongodb://localhost:27017`
- **Database:** `plp_bookstore`
- **Collection:** `books`

### Key Features Used

- **Documents Tab:** View and edit documents
- **Aggregations Tab:** Build aggregation pipelines visually
- **Schema Tab:** Analyze data structure and field types
- **Indexes Tab:** Create and manage indexes
- **Explain Plan:** Analyze query performance
- **Validation Tab:** Set up document validation rules

### Compass Aggregation Examples

You can build these aggregations visually in Compass:

1. **Genre Statistics Pipeline**
2. **Author Analysis Pipeline** 
3. **Price Range Analysis**
4. **Publication Timeline**

## Project Structure

```
mongodb-bookstore-project/
├── README.md
├── sample-data/
│   └── books.json
├── queries/
│   ├── 01-basic-crud.js
│   ├── 02-advanced-queries.js
│   ├── 03-aggregations.js
│   ├── 04-indexing.js
│   └── 05-performance-tests.js
├── scripts/
│   ├── setup-database.js
│   ├── create-indexes.js
│   └── sample-queries.js
├── docs/
│   ├── query-examples.md
│   ├── aggregation-pipelines.md
│   └── performance-guide.md
└── screenshots/
    ├── compass-overview.png
    ├── query-results.png
    ├── aggregation-results.png
    └── performance-comparison.png
```

## Troubleshooting

### Common Issues

#### 1. Connection Issues

**Problem:** `MongoNetworkError: connect ECONNREFUSED 127.0.0.1:27017`

**Solutions:**
- Start MongoDB service: `net start MongoDB` (Windows) or `sudo systemctl start mongod` (Linux)
- Check if MongoDB is running: `sudo systemctl status mongod`
- Verify MongoDB installation
- Check firewall settings

#### 2. Database Access Issues

**Problem:** Cannot access `plp_bookstore` database

**Solutions:**
- Ensure you've switched to the correct database: `use plp_bookstore`
- Verify database exists: `show dbs`
- Check collection exists: `show collections`

#### 3. Query Performance Issues

**Problem:** Slow query execution

**Solutions:**
- Create appropriate indexes
- Use `.explain()` to analyze query execution
- Limit result sets with `.limit()`
- Use projection to reduce data transfer

#### 4. Compass Connection Issues

**Problem:** MongoDB Compass won't connect

**Solutions:**
- Use connection string: `mongodb://localhost:27017`
- Verify MongoDB service is running
- Check authentication requirements
- Try connecting via MongoDB Shell first

#### 5. Index Creation Errors

**Problem:** Cannot create indexes

**Solutions:**
- Ensure you have write permissions
- Check for existing indexes with same name
- Verify correct syntax
- Check available disk space

## Learning Objectives

After completing this project, you will have mastered:

- ✅ **MongoDB Installation & Setup**
  - Installing MongoDB Community Edition
  - Starting and stopping MongoDB service
  - Using MongoDB Shell (mongosh)

- ✅ **Basic CRUD Operations**
  - Creating documents with `insertOne()` and `insertMany()`
  - Reading data with `find()` and `findOne()`
  - Updating documents with `updateOne()` and `updateMany()`
  - Deleting documents with `deleteOne()` and `deleteMany()`

- ✅ **Advanced Query Techniques**
  - Complex filtering with multiple conditions
  - Using comparison operators (`$gte`, `$lt`, `$in`, etc.)
  - Regular expressions for text matching
  - Sorting and pagination
  - Field projection

- ✅ **Aggregation Pipeline Mastery**
  - Grouping data with `$group`
  - Calculating statistics with `$avg`, `$sum`, `$min`, `$max`
  - Sorting aggregation results
  - Using `$project` for field transformation

- ✅ **Index Creation & Performance Optimization**
  - Creating single field indexes
  - Building compound indexes
  - Text indexes for search functionality
  - Performance analysis with `explain()`
  - Index management and maintenance

- ✅ **MongoDB Compass Proficiency**
  - Visual query building
  - Aggregation pipeline construction
  - Schema analysis
  - Performance monitoring

- ✅ **Real-world Database Design Principles**
  - Document structure design
  - Field naming conventions
  - Data type selection
  - Performance considerations

## Expected Results

### Sample Query Results

**Database Statistics:**
- **Total Books:** 12
- **Unique Genres:** 8 (Fiction, Fantasy, Dystopian, Romance, Science Fiction, etc.)
- **Authors with Multiple Books:** George Orwell (2), J.R.R. Tolkien (2)
- **Price Range:** $7.99 - $19.99
- **Publication Years:** 1813 - 2025
- **Books in Stock:** 9
- **Books Out of Stock:** 3

**Performance Metrics:**
- **Without Indexes:** COLLSCAN on all queries
- **With Indexes:** IXSCAN for indexed fields
- **Query Time Improvement:** 90%+ for indexed queries
- **Documents Examined:** Reduced from 12 to 1-2 for specific queries

**Top Genres by Book Count:**
1. Fiction (3 books)
2. Fantasy (3 books)
3. Dystopian (3 books)
4. Romance (2 books)

**Author Statistics:**
- George Orwell: 2 books, avg price $11.49
- J.R.R. Tolkien: 2 books, avg price $16.49

## Contributing

This is an educational project designed for learning MongoDB fundamentals. You can extend it with additional features:

### Beginner Extensions
- Add more book documents
- Create queries for different genres
- Experiment with different aggregation pipelines
- Practice index creation and removal

### Intermediate Extensions
- **User Management System**
  - Add user collection
  - Implement user authentication
  - Track user book preferences

- **Order Management**
  - Create orders collection
  - Track book purchases
  - Calculate sales statistics

- **Inventory Tracking**
  - Track stock quantities
  - Implement low-stock alerts
  - Manage supplier information

### Advanced Extensions
- **RESTful API Integration**
  - Build Express.js API
  - Implement CRUD endpoints
  - Add authentication middleware

- **Search Functionality**
  - Advanced text search
  - Faceted search options
  - Search result ranking

- **Analytics Dashboard**
  - Sales reporting
  - Inventory analytics
  - Customer behavior analysis

- **Data Validation**
  - JSON Schema validation
  - Custom validation rules
  - Error handling

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



