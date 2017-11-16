### Sprint 1: Webscraping NFL Depth Chart Using RStudio (rvest)

11/07/17 - 11/16/2017:

**Author:** Olina Cavedoni

__*Project Description:*__
\n The objective of this first project was to create a code script to retrieve football player names and positions from an online NFL depth chart. This is part of a larger project in which the goal is to have a product that automatically projects weekly Fantasy Football player points.

__*Steps:*__

HTML
- Open link to NFL Depth Chart in Google Chrome: http://subscribers.footballguys.com/apps/depthchart.php?type=noidp&lite=yes&exclude_coaches=yes
- Right Click, choose "Inspect" to open the Developer Panel
- Click on the "Selector" tool on the top left of the Developer Panel in order to inspect a selected element on the HTML page
- Select the tables with the table names, note that the player data is under the tag ".la"

RStudio
- Open RStudio
- In the console, insert the following code which will return a list of all players and positions on the depth chart:

\n  *install.packages("rvest")*
    - Installs rvest, a package within RStudio that makes it easy to scrape data from html webpages.
\n  *library(rvest)*
    - Loads the rvest package.
\n  *url <- 'http://subscribers.footballguys.com/apps/depthchart.php?type=noidp&lite=yes&exclude_coaches=yes'*
    - Associates "url" with the website to be scraped.
\n  *webpage <- read_html(url)*
    - Reads the HTML code from the specified website.
\n  *nflplayers_html <- html_nodes(webpage, '.la')*
    - Uses the CSS selectors to scrape the sections with class ".la"
\n  *nflplayers_text <- html_text(nflplayers_html)*  
    - Converts the HTML data into text format.
\n  *nflplayers_text*
    - Displays data.

Excel
- Copy and past data from RStudio into excel (in the interest of time)
- Clean data
    - Delete unnecessary rows (1, 18, 35, and 36)
    - Delete unnecessary positions (FB)
    - Data > Text to Columns
    - Separate player names from positions (=LEFT(CELL#, LEN(CELL#)-2))
- Format data
    - Add headers (Position Type + Position Number, e.g. RB1, WR3, TE2, etc. )
    - Change color of headers and columns separating player positions (dark blue)
    - Add color to cells with players depending on if they are in starting positions or not (light blue, light gray)
    - Change border colors (white)
    - Add conditional formatting to identify injured players (Text that contains "(inj)")

    Done!
