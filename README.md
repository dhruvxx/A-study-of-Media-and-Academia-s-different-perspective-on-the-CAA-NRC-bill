# A-study-of-Media-and-Academia-s-different-perspective-on-the-CAA-NRC-bill

Analysing academic articles and articles published on media (online newspapers) on a particular issue (CAA-NRC bill) and noticing the differences between the perspectives through which the media and academia study it.

For the initial part, data from four online newspaper sources have been scraped - namely The Hindu, Hindustan Times, The Telegraph and The Times of India.

This data, for the purpose of initial analysis have been put through the following processes:

- Preprocessing: The data from each article has been cleaned and the numbers have been removed at this stage to get rid of noise.
- Processing: Various pickle files have been created where the data has been segregated into various sections according to the date of publishing for easier access while forming wordclouds and topic modelling.
- Wordclouds: Word clouds or tag clouds are graphical representations of word frequency that give greater prominence to words that appear more frequently in a source text. The larger the word in the visual the more common the word was in the document(s). To obtain an insight into the content of the articles scraped, wordclouds of the csvs have been formulated, per month and as a whole.
- Topic Modelling: Topic models can help to organize and offer insights for us to understand large collections of unstructured text bodies. Originally developed as a text-mining tool, topic models have been used to detect instructive structures in data such as genetic information, images, and networks. This has also ben done for all the scraped data, segregated into date stamps.

Inside the initial analysis folders:

- Codes: contains the codes used to pre-process and process the scrape the data, form word clouds and topic model.
- Scraping: contains the spiders used to scrape the articles.
- Freq: Contains a liost of all the words that have come up the most frequently in these articles. it is important to note that a variety of stopwords are still present in these files, and are hence unusable for analysis. The main purpose for the creation of these files is to know what stopwords to include in the secondary layer of screening.
- Wordclouds: contains wordclouds formed on the data for the actual data as is, the steemed version and the lemmatized version.
- Topic models: contains the topic models of the data, segregated by date in json files.

# EPW

```
EPW/
├── articles_per_month.csv
├── articles_per_year.csv
├── cleaned_engage_articles.txt
├── datewise_text_dict.pkl
├── engage_articles.txt
├── epw_caanrc_processed.csv
├── topic_models
│   ├── lda_decadely_topics.json
│   └── lsa_decadely_topics.json
└── wordclouds
    ├── 2019_Dec.svg
    ├── 2020_Apr.svg
    ├── 2020_Feb.svg
    ├── 2020_Jan.svg
    ├── 2020_Mar.svg
    ├── after_covid.svg
    └── before_protests.svg
```

- Delimiter is `"|"` for all CSVs
- `articles_per_month.csv` and `articles_per_year.csv` are the number of articles per month (in separate years) and years
- `cleaned_engage_articles.txt` and `engage_articles.txt` is because engage articles dont have date and authors, so entered manually
- `datewise_text_dict.pkl` a python dictionary with the concatenated text for before protests, Dec 2019, Jan-Apr 2020, and after covid periods. Used for Wordclouds. Similar approach also used for Topic modelling.

## RESULTS

- `wordclouds/` contains wordclouds
- `topic_models/` contains LSA and LDA generated topic models

## DATA

`epw_caanrc_processed.csv`

- First line of the csv is the header: `url|clean_url|title|date|authors|content|year|month`
  - clean_url is without cache and IP suffix.
  - date includes the volume and issue number
- 207 articles in total
- Contains all EPW artciles from 1965-2022 with any of the title or content containing any of the following phrases:
  - caa
  - nrc
  - citizenship amendment bill
  - citizenship amendment act
  - caa nrc
  - cab nrc
  - national register of citizens
  - citizenship bill
  
### Contributors

Pranoy J
Sarthak Agrawal
Pravalika Mukkiri
Dhruvee Birla
Aaradhya Gupta
Harshdeep Singh
