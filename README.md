# OrderBook
import bisect
import pandas as pd
Next, we declare the Orderbook class and initialize the attributes. For now, we will skip the documentation comments.
First, Orderbook inherits from object – the default in Python 3. order_history is a list of all of the orders sequenced by arrival time.
_add_order_to_history adds a unique order index to an existing order (dict) and appends the modified order to the order_history list.
_modify_order behaves similarly, but also checks if the modify actually results in removal.
_confirm_trade and _confirm_modify are helper functions that append trade or modify messages to a list that is conveyed to the traders.
process_order determines whether an incoming order results in a match with a resting order or not.
_match_trade enforces price-time priority for matching incoming orders against resting orders.
Three helper functions facilitate saving data to an hdf5 for use after the simulation has ended.
The final function is a public method for conveying the top of book information to the traders.
