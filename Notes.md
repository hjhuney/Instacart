# Things to Explore

* Day of week / time of day stats
* Reordered items
* Most popular items
* Item combos
* Frequency of orders for user

## User-Based Collaborative Filtering

* Built matrix of things each user bought / viewed / rated / etc
* Compute similarity scores between users
* Find users similar to you
* Recommend stuff they bought / viewed / rated that you haven't

## Item-Based Collaborative Filtering

* Built on relationships between items rather than people
* Normally less things than people; harder to game system
* Find every pair of items bought / viewed / etc by same person
* Measure similarity of ratings across all users who bought / viewed / both
* Sort by movie, then by similarity strength
