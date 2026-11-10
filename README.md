

# Python Blog Application

blogs = []

def add_blog():
    title = input("Enter Blog Title: ")
    author = input("Enter Author Name: ")
    content = input("Enter Blog Content: ")

    blog = {
        "title": title,
        "author": author,
        "content": content
    }

    blogs.append(blog)
    print("Blog added successfully!")

def view_blogs():
    if len(blogs) == 0:
        print("No blogs available!")
    else:
        print("\n===== All Blog Posts =====")

        for i, blog in enumerate(blogs, start=1):
            print("\nBlog No:", i)
            print("Title:", blog["title"])
            print("Author:", blog["author"])
            print("Content:", blog["content"])

def search_blog():
    title = input("Enter blog title to search: ").lower()

    found = False

    for blog in blogs:
        if title in blog["title"].lower():
            print("\nBlog Found!")
            print("Title:", blog["title"])
            print("Author:", blog["author"])
            print("Content:", blog["content"])
            found = True

    if not found:
        print("Blog not found!")

def delete_blog():
    title = input("Enter title of blog to delete: ").lower()

    for blog in blogs:
        if blog["title"].lower() == title:
            blogs.remove(blog)
            print("Blog deleted successfully!")
            return

    print("Blog not found!")

while True:
    print("\n===== BLOG APPLICATION =====")
    print("1. Add Blog")
    print("2. View Blogs")
    print("3. Search Blog")
    print("4. Delete Blog")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_blog()

    elif choice == "2":
        view_blogs()

    elif choice == "3":
        search_blog()

    elif choice == "4":
        delete_blog()

    elif choice == "5":
        print("Thank you for using Blog Application!")
        break

    else:
        print("Invalid choice! Try again.")
