# SQLAlchemy Query Exercises

### 1. Create one article with a title and subtitle.

```python
article = Article(title="My Title", subtitle="My Subtitle")
db.session.add(article)
db.session.commit()
```

### 2. Retrieve all books with the title "Ulysses".

```python
books = Book.query.filter_by(title="Ulysses").all()
```

### 3. Update a user's first name to "Nicholas".

```python
user = User.query.get(user_id)
user.first_name = "Nicholas"
db.session.add(user)
db.session.commit()
```

### 4. Fetch all reservations.

```python
reservations = Reservation.query.all()
```

### 5. Create a comment with a content written by a user with id of 2534.

```python
comment = Comment(content="My comment", user_id=2534)
db.session.add(comment)
db.session.commit()
```

### 6. Fetch one room by id (passed in as 'room_id').

```python
room = Room.query.get(room_id)
```

### 7. Delete a reservation by id (passed in as 'reservation_id').

```python
Reservation.query.filter_by(id=reservation_id).delete()
db.session.commit()
```

### 8. Fetch a review, and if its view count is > 100, update it as a top review (top_review Boolean).

```python
review = Review.query.get(review_id)
if review.view_count > 100:
    review.top_review = True
    db.session.add(review)
    db.session.commit()
```
