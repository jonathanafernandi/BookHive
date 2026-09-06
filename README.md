# BookHive

BookHive is a prototype Laravel-based web application for book borrowing and library management, developed as a group project for the COMP6821001 – Web Development course. It provides role-based access for administrators to manage the book catalog and for users to browse, borrow, review, and wishlist books.

## Table of Contents

- [Overview](#overview)
- [Group Members](#group-members)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [User Roles](#user-roles)
- [Getting Started](#getting-started)

## Overview

BookHive centralizes book lending operations in a single web platform. Administrators can maintain the book catalog (add, edit, delete titles), while registered users can search the catalog, borrow and return books, maintain a personal wishlist, and leave ratings and reviews for books they have read.

## Group Members

| Name | Student ID |
|---|---|
| Jonathan Alvindo Fernandi | 2602089143 |
| Muhammad Farras Fadhilah | 2301889685 |
| Juan Nathan Waraney Tombeng | 2301922934 |
| Berlianta Abdussalam | 2440098060 |

**Course**: COMP6821001 – Web Development  
**Class:** LR01 (Group 3)

## Tech Stack

| Layer | Technology |
|---|---|
| Backend Framework | Laravel |
| Database | MySQL |
| Frontend | Blade templates |
| Authentication | Laravel's built-in authentication scaffolding |

## Features

### Authentication
- Register a new account (Name, Email, Password, Confirm Password).
- Log in with "Remember me" session persistence.
- Password reset via emailed reset link ("Forgot your password").
- Profile management: update name/email, change password, or delete account (with password confirmation).

### Book Management (Admin)
- Add a new book (Title, Author, Category, Stock).
- Edit existing book details.
- Delete a book from the catalog (with confirmation dialog).

### Book Browsing & Borrowing (User)
- Browse the paginated Book List with search functionality.
- View detailed book information (Title, Author, Category, Stock) on the Show Book page.
- Add or remove a book from a personal Wishlist.
- Borrow a book by entering the borrower's name; borrowing records are logged in the Borrow History.
- Return a borrowed book.
- Submit a rating and comment as a book review, recorded in the Reviews table.

## User Roles

| Role | Capabilities |
|---|---|
| **Admin** | Full book catalog management (add/edit/delete), plus all user capabilities |
| **User** | Browse, borrow, return, wishlist, and review books; manage own profile |

Role-based access is enforced via Laravel middleware.

## Getting Started

### Prerequisites

- PHP 8.1+
- Composer
- MySQL

### Installation

```bash
git clone https://github.com/jonathanafernandi/BookHive.git
cd BookHive
composer install
cp .env.example .env
php artisan key:generate
```

Configure your database credentials in `.env`, then run:

```bash
php artisan migrate --seed
php artisan serve
```

Visit `http://localhost:8000` to access the application. Demo admin and user accounts are seeded automatically; refer to the team's internal documentation for credentials, or register a new account directly through the Register page.
