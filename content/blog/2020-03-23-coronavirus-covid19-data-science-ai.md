---
author: JohnGriffin
date: "2020-03-23"
published: true
title: "What can data scientists contribute to the COVID-19 effort?"
header_image: ""
---


<iframe src="https://ourworldindata.org/grapher/total-covid-deaths-per-million" style="width: 100%; height: 600px; border: 0px none;"></iframe>

<br><br>
Health care professionals are the real heroes of the moment but there is an important role for data scientists to play in the fight against the pandemic that’s shaking the globe right now.

Your first port of call should be the [COVID-19 Open Research Dataset](https://pages.semanticscholar.org/coronavirus-research) — released on 20th March by the White House and a coalition of leading research groups. I recommend heading over to the associated [Kaggle](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) competition where you can collaborate and build upon the work of other data scientists who have already made progress on cleaning and understanding the potential of this dataset containing over 29,000 academic papers related to COVID-19, SARS-CoV-2, and other coronaviruses.


This looks like a natural language understanding problem to data scientists but it is essential that we also have the involvement of medical professionals to direct and sense check the work that’s ongoing.

## Goals

Current tasks defined in the Kaggle competition include:

*   What is known about transmission, incubation, and environmental stability?
*   What do we know about COVID-19 risk factors?
*   Help us understand how geography affects virality.
*   What do we know about virus genetics, origin, and evolution?
*   What has been published about ethical and social science considerations?
*   What has been published about medical care?
*   What has been published about information sharing and inter-sectoral collaboration?
*   What do we know about vaccines and therapeutics?
*   What do we know about diagnostics and surveillance?
*   What do we know about non-pharmaceutical interventions?

In order to prioritise tasks it’s important to understand both what can make the most impact to the HCPs on the ground but also what tasks the data can adequately support. Some work has been done on this already by [scoring the relative tasks on a five-point scale](https://docs.google.com/spreadsheets/d/1AhDif1UUVFJAQjYM8UcbKSPXUFe0hRXfFnMkcdw3YmI/edit#gid=1419477211):

*   <b>Impact</b> — what would be the magnitude of the impact?
*   <b>Data presence</b> — is there meaningful data available?
*   <b>Similar solutions</b> — have we solved similar problems with ML before?
*   <b>Specificity</b> — how concrete is the definition of the need?
*   <b>Simplicity</b> — how simple/complex is the solution?

<img src="/images/covid-sheet.png">

The problem faced here is that the people who are voting seem to have quite divergent opinions on these ratings, it seems likely that people may only have partial knowledge and answering the question of data presence is a significant task in itself.

## Organisation

Decentralised coordination is currently happening in a few different groups. I’ll point to one group in particular as I see momentum there and I think there is value in centralising coordination to some extent in order to avoid duplication of effort. There are currently over 230 members on the Slack.

*   [Discussion page for the COVID-10 Global group on Kaggle](https://www.kaggle.com/arturkiulian/covid-19-global-team-collaboration-join-slack)
*   [Trello](https://trello.com/b/y4odX7yZ/covid-19-global-team)
*   [Slack](https://join.slack.com/t/coronawhy/shared_invite/zt-cw83m6ds-p4AwsMV65tha2joKhn~s5Q)

If you have data science or visualisation skills, or if you have a medical background and can contribute some time then please stop by the [Slack](https://join.slack.com/t/coronawhy/shared_invite/zt-cw83m6ds-p4AwsMV65tha2joKhn~s5Q) and introduce yourself.

## Other Data Sources

Some excellent work is being done all over the place at the moment and so I’ll link to a few other data sources that might be interesting.

*   [https://covidtracking.com/](https://covidtracking.com/) — The COVID Tracking Project collects information from 50 US states, the District of Columbia, and 5 other US territories to provide the most comprehensive testing data we can collect for the novel coronavirus, SARS-CoV-2. We attempt to include *positive and negative results*, *pending tests*, and *total people tested for* each state or district currently reporting that data.
*   [UK COVID-19 cases by day broken down by local authority](https://www.arcgis.com/apps/opsdashboard/index.html#/f94c3c90da5b4e9f9a0b19484dd4bb14)
*   [Health Data Research UK Github — contains links to various UK-specific datasets](https://github.com/hdruk/covid-19)
*   [Our World in Data Statistics](https://ourworldindata.org/coronavirus) — these are excellent and contain a foreword regarding why these numbers are more reliable than the WHO data.

Day level cases data by geography:

*   India — [https://www.kaggle.com/sudalairajkumar/covid19-in-india](https://www.kaggle.com/sudalairajkumar/covid19-in-india)
*   South Korea — [https://www.kaggle.com/kimjihoo/coronavirusdataset](https://www.kaggle.com/kimjihoo/coronavirusdataset)
*   Italy — [https://www.kaggle.com/sudalairajkumar/covid19-in-italy](https://www.kaggle.com/sudalairajkumar/covid19-in-italy)
*   Brazil — [https://www.kaggle.com/unanimad/corona-virus-brazil](https://www.kaggle.com/unanimad/corona-virus-brazil)
*   USA — [https://www.kaggle.com/sudalairajkumar/covid19-in-usa](https://www.kaggle.com/sudalairajkumar/covid19-in-usa)
*   Switzerland — [https://www.kaggle.com/daenuprobst/covid19-cases-switzerland](https://www.kaggle.com/daenuprobst/covid19-cases-switzerland)
*   Indonesia — [https://www.kaggle.com/ardisragen/indonesia-coronavirus-cases](https://www.kaggle.com/ardisragen/indonesia-coronavirus-cases)
