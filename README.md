# Co-Authorship Network Analysis

CZ4071 - Network Science

Analyse networks between SCSE faculty members and explain its reputation growth.

## Setup

    pip install -r requirements.txt

## Preprocessing

Preprocessing is done to generate the graph. We preprocess **Faculty.xlsx** by adding the PID from DHLP and using it as the identifier for the faculty member, producing **Faculty.csv.** We then scrap data from their DHLP site in the form of XML files to create **Papers.csv.** We preprocess **Top.xlsx** by manually looking for matching journal conference names in the XML files as seen in the new column "DHLP_Venue" in **Top.xlsx**.

To generate the graph, we define a node as a faculty member with the following attributes:

1.  Name
2.  Position
3.  Mgmt - Whether the faculty member has held a management position (Y/N)
4.  Gender
5.  Area - Research area of faculty member
6.  is_excellent - Whether the faculty member has published at top conferences from Top.xlsx
7.  min_date = First publication by the member [For filtering across time]

We define an edge to be formed between 2 nodes if and only if the 2 nodes have collaborated on the same publication. Hence the edge also contains information about the publication's title, date, and journal. There might be multiple publications in the edge between the 2 nodes that have collaborated more than once.

## Usage

Run `python project.py` after setup.
