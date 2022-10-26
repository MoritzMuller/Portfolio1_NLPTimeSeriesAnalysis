# Portfolio: NLP/TimeSeries Analysis of European Central Bank communication with the media

This is work that I have done for  my PhD, more specifically for the paper "Guiding or Following the Crowd? Strategic communication as regulatory and reputational strategy" by myself (Moritz Müller) and Caelesta Braun. All the coding and statistical analysis that you see in this document was done by me. 

The basic question of the paper is the following: Does the European Central Bank influence the topics that the news media reports about, or does it work the other way around? This is a hugely relevant question, as the ECB relies on good newspaper reporting, particularly duing financial crises: Newspapers drastically influence public sentiment regarding financial stability. If the public falls into panic, the financial system (stock markets, bond markets, pension systems, etc.) will follow. 

Due to copyright issues, I cannot share the newspaper dataset - however, I will show every step of the analysis and provide glimpses into the various decisions, cleaning steps, and other decisions that were made. 

To do this, I combine natural language processing and time series analysis. More specifically, I have scraped all communication of the European Central Bank from their website (via Octoparse). This includes Interviews, monetary decisions, Press Conference transcripts, Speeches, and Press releases. For the news media data, I have scraped all available newspaper articles from major Euopean outlets that contain the word "ECB" or "European Central Bank".

I followed the following strategy: 
1. Clean all data.
2. Enrich/ wrangle the data wherever possible (i.e., add other relevant datapoints).
3. Fit topic models to the ECB corpus to extract relevant topics from the text.
4. Create a dictionary of words that capture the the three most relevant topics, but across source contexts. --> Applying the ECB topic model to the newspaper corpus is not feasible, since the newspapers tend to use different wording for simliar topics than the European Central Bank would. A dictionary is technologically less advanced, but proved to be a more reliable tool than topic models. At the same time, I still use the topic models to identify key terms.
5. Run the dictionary on both the ECB and newspaper corpus. This results of 6 time series: 3 topics in both text corpora.
6. Perform time series analysis, more specifically VAR models and impulse-response functions. This is to test whether the time series of one topic in one text corpus influences the time series of the same topic in the other corpus.


For an easy runthrough with comments, find the rMarkdown file here: https://htmlpreview.github.io/?https://github.com/MoritzMuller/Portfolio1_NLPTimeSeriesAnalysis/blob/main/ECB_portfolio.html
