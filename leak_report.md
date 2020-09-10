# Leak report

The leak that I found originated in ```strip()```, but actually manifested itself in ```is_clean()```
 when the variable ```cleaned``` was set. To fix this, I needed to not only add ```free(cleaned)``` after
 ```cleaned``` was done being used, but I also needed to make it conditional in the event that cleaned
 was not actually used and empty since free() would throw an error otherwise.
