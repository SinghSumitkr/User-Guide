Smart Search
Smart Search is a global search tool in Qlik Sense that allows users to search through the entire data set within a dashboard. This feature can be accessed from the Selections Bar (top ribbon in the dashboard) by clicking the search icon.

Key Features of Smart Search
Text-Based Search Only: Smart Search supports only text searches. Other search operators, except for quotation marks (" "), are not supported.
Searchable Data Items:
Field Values: Search matches against field values present in the dataset.
Dimension Values: Search matches against dimension values available in the visualizations.
Exclusion of Measure Values: Smart Search does not include measures (measure values) in the search results.
How Smart Search Works
Entering Search Text: As you type in the search field, Smart Search filters the field and dimension values and displays the matching items.
Handling of Spaces in Search Terms: If your search contains spaces (e.g., "mountain bike"), Qlik Sense considers them as separate search terms. To link multiple words into a single search term, enclose them in quotation marks (e.g., “mountain bike”).
Color-Coded Search Terms: When searching for multiple items separated by spaces, each search term is assigned a unique color code. This helps in distinguishing between full and partial matches in the search results.
Important Notes
Search Behavior: Smart Search always compares search terms against the beginning of the words in the database. For instance, searching for "read" would match "reader" and "Reading," but not "bread."
Keyboard Shortcuts
Open Smart Search: Ctrl + F
Close Smart Search: Esc
By leveraging Smart Search, users can quickly navigate and filter data within their Qlik Sense dashboards, enhancing their data exploration and analysis experience.
