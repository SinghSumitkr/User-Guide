User Guide: Selections and Search Options
Overview
During analysis, your selections are displayed above the sheet. Each selection item has a small bar at the bottom reflecting its state within that dimension. The bar can show three different states:

Selected (green)
Alternative (light gray)
Excluded (dark gray)
Locked values are displayed with a lock icon. When you click a selection item, a pop-up menu appears, allowing you to:

View the selection
Edit or clear the selection
Search for dimension values
Lock the selection
If you are using alternate states in the app, you will see those selections in the selection bar. The field in an alternate state will display the number of alternate states, allowing you to:

Click on the field to view states
Click on a state to see its selections
Clear the selections for that state or clear all selections
Selection Options
1. Select All
All values are selected and marked as selected.
Alternative values (light gray) change to selected (green), and excluded values (dark gray) change state to selected excluded.
Clearing the selections that caused exclusion will change those values to selected (green).
2. Select Possible
All possible values (white) are selected.
This option is not available within a selection item, but in a filter pane, possible values may result from another selection.
3. Select Alternative
In fields where a selection has been made, alternative values (light gray) represent values that would have been possible if no selection had been made.
Selecting alternative values turns previously selected values into alternative.
4. Select Excluded
If alternative values are present, they will be selected, and the previously selected values will become alternative.
If no alternative values are available, the excluded values are selected, and the previously selected values become alternative.
Searching within Selections or Visualizations
You can search for values and make selections from the filtered results. Search options are available in the selection bar and within visualizations such as filter panes and tables. Searches are not case sensitive.

Search Types
1. Normal Search
Displays strings that match the search string. If multiple strings are separated by spaces, they are interpreted as separate search strings.
Wildcards are not allowed, but you can use plus (+) and minus (-) modifiers.
Examples:

"orange juice" → Finds only field values containing "orange juice".
orange juice → Finds fields containing either "orange" or "juice".
-orange -juice → Excludes results containing "orange" or "juice".
+orange +juice → Finds matches like "orange juice" or "orange and apple juice".
2. Wildcard Search
Does not support plus or minus modifiers.
Supports the following wildcards:
* → Matches any sequence of characters.
? → Matches any single character (e.g., r?ck matches four-letter words starting with "r" and ending with "ck").
^ → Starts the match at the beginning of a string.
3. Expression Search
Begins with an equals sign (=).
Used to search for values across all fields associated with the search field.
Example:
=Sum(Sales) > 1000000 in the Customer field returns all customers with sales greater than 1,000,000.
