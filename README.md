# CodSoft-by-karthik-task-Recommendation-System-
The goal of this task is to design and implement a simple recommendation system that suggests items to users (like movies, books, or videos) based on their preferences. Recommendation systems are widely used in platforms such as Netflix, YouTube, and Amazon to improve user experience by showing personalized suggestions.

# Simple Recommendation System (Content-Based)

data = {
    "Movies": {
        "Inception": "Sci-Fi",
        "Avengers": "Action",
        "Titanic": "Romance",
        "The Notebook": "Romance",
        "Interstellar": "Sci-Fi",
        "John Wick": "Action"
    },
    "Books": {
        "Harry Potter": "Fantasy",
        "The Hobbit": "Fantasy",
        "Sherlock Holmes": "Mystery",
        "Da Vinci Code": "Mystery",
        "Pride and Prejudice": "Romance",
        "Twilight": "Romance"
    },
    "Videos": {
        "Python Tutorial": "Education",
        "AI Basics": "Education",
        "Football Highlights": "Sports",
        "Cricket World Cup": "Sports",
        "Funny Cats": "Entertainment",
        "Stand-up Comedy": "Entertainment"
    }
}

def recommend(category, preference):
    print(f"\nRecommended {category} ({preference}) for you:")
    items = data.get(category, {})
    found = False
    for item, genre in items.items():
        if genre.lower() == preference.lower():
            print("-", item)
            found = True
    if not found:
        print("sorry dude🙂! Try another category or preference.")

# User Interaction
print("Categories: Movies, Books, Videos")
category = input("Choose a category: ")

if category in data:
    unique_genres = set(data[category].values())
    print(f"Available genres in {category}: {', '.join(unique_genres)}")
    pref = input("Enter your favorite genre: ")
    recommend(category, pref)
else:
    print("Invalid category! Please choose Movies, Books, or Videos.")
