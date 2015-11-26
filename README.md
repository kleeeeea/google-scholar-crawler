
## google-scholar-crawler

#### You can start the crawler with a start_url:

```
cd googlescholar
scrapy crawl googlescholar -a start_url="https://scholar.google.com/scholar?hl=en&q=estimate+ctr&btnG=&as_sdt=1%2C5&as_sdtp="
```

#### Core code, super easy, isn't it?

```
    list_css_rules = {
        '.gs_r': {
            'title': '.gs_rt a *::text',
            'url': '.gs_rt a::attr(href)',
            'related-text': '.gs_ggsS::text',
            'related-type': '.gs_ggsS .gs_ctg2::text',
            'related-url': '.gs_ggs a::attr(href)',
            'citation-text': '.gs_fl > a:nth-child(1)::text',
            'citation-url': '.gs_fl > a:nth-child(1)::attr(href)',
            'authors': '.gs_a a::text',
            'description': '.gs_rs *::text',
            'journal-year-src': '.gs_a::text',
        }
    }

    def parse_1(self, response):
        info('Parse '+response.url)
        x = self.parse_with_rules(response, self.list_css_rules, dict)
        pp.pprint(x[0]['.gs_r'])
```

#### Example results

```
[{'authors': u'M Richardson',
  'citation-text': u'Cited by 418',
  'citation-url': [u'/scholar?cites=7775706795797520334&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  Note that, because the probability of clicking on an ad drops so significantly with ad position,  the accuracy with which we  estimate  its  CTR  can have a significant effect on revenues.  ...  For any  ad that has been displayed a significant number of times, we can easily  estimate  its  CTR .  ...',
  'journal-year-src': u', E Dominowska, R Ragno - Proceedings of the 16th \u2026, 2007 - dl.acm.org',
  'related-text': u'microsoft.com ',
  'related-type': u'[PDF]',
  'related-url': [u'http://research.microsoft.com/en-us/um/people/mattri/papers/www2007/predictingclicks.pdf'],
  'title': u'Predicting clicks: estimating the click-through rate for new ads',
  'url': [u'http://dl.acm.org/citation.cfm?id=1242643']},
 {'authors': '',
  'citation-text': u'Cited by 132',
  'citation-url': [u'/scholar?cites=3862680228943341001&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  assumed. However, sponsored search opportunities may arise and we may wish to estimate CTR  in the absence of history on the specific search term. Such an  ...  period.  This is the broadest possible  estimate  of  CTR . Prediction method  ...',
  'journal-year-src': u'M Regelson, D Fain - Proceedings of the Second Workshop on Sponsored \u2026, 2006 - diyhpl.us',
  'related-text': u'diyhpl.us ',
  'related-type': u'[PDF]',
  'related-url': [u'http://diyhpl.us/~bryan/papers2/marketing/Predicting%20click-through%20rate%20using%20keyword%20clusters.pdf'],
  'title': u'Predicting click-through rate using keyword clusters',
  'url': [u'http://diyhpl.us/~bryan/papers2/marketing/Predicting%20click-through%20rate%20using%20keyword%20clusters.pdf']},
 {'authors': '',
  'citation-text': u'Cited by 256',
  'citation-url': [u'/scholar?cites=4179736953804976561&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  Thus the  estimate  given above for the electric moment required to VOL. 37 N Page 4. 340  Discussion 0%  ...  Observations of the sign and magnitude of the intense potential gradients below  thunderclouds will also help towards obtaining some  estimate  of the currents.  ...',
  'journal-year-src': u'Wilson - Proceedings of the Physical Society of London, 1924 - iopscience.iop.org',
  'related-text': '',
  'related-type': '',
  'related-url': [],
  'title': u'The electric field of a thundercloud and some of its effects',
  'url': [u'http://iopscience.iop.org/1478-7814/37/1/314']},
 {'authors': u'AE Lugo',
  'citation-text': u'Cited by 62',
  'citation-url': [u'/scholar?cites=12106933117404728992&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  1982. All leaf scars were counted to  estimate  leaf production rate, and the distance  between scars was measured to establish relationships between leaf production  and height growth. Height  ...  relevance.  Estimate  of age. The  ...',
  'journal-year-src': u',  Batlle - Journal of Tropical Ecology, 1987 - Cambridge Univ Press',
  'related-text': '',
  'related-type': '',
  'related-url': [],
  'title': u'Leaf production, growth rate, and age of the palm Prestoea montana in the Luquillo Experimental Forest, Puerto Rico',
  'url': [u'http://journals.cambridge.org/abstract_S0266467400001905']},
 {'authors': u'L Li W Chu J Langford',
  'citation-text': u'Cited by 105',
  'citation-url': [u'/scholar?cites=11791874182992109343&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u"...  of payoff, the expected payoff of an article is precisely its click-through rate ( CTR ), and choosing  an article with maximum  CTR  is equivalent  ...  However, obtaining information about the arms' av-  erage payoffs (ie, exploration) can refine A's  estimate  of the arms' payoffs and in turn  ...",
  'journal-year-src': u',  ,  , X Wang - \u2026 conference on Web search and data \u2026, 2011 - dl.acm.org',
  'related-text': u'arxiv.org ',
  'related-type': u'[PDF]',
  'related-url': [u'http://arxiv.org/pdf/1003.5956'],
  'title': u'Unbiased offline evaluation of contextual-bandit-based news article recommendation algorithms',
  'url': [u'http://dl.acm.org/citation.cfm?id=1935878']},
 {'authors': u'RC Bourge',
  'citation-text': u'Cited by 55',
  'citation-url': [u'/scholar?cites=1749919671871135917&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  This included the demographic and clinical variables included in Phase 1 plus 3 additional  variables of interest: (1) the probability  estimate  (risk) of rejection death at 1 year for each patient  based on the Phase 1 analysis; (2) the use or non-use of induction therapy; and (3) the  ...',
  'journal-year-src': u'\u2026, L Miller, M Flattery,  ,  Database - The Journal of heart and \u2026, 2005 - Elsevier',
  'related-text': u'jhltonline.org ',
  'related-type': u'[HTML]',
  'related-url': [u'http://www.jhltonline.org/article/S1053-2498(04)00034-8/abstract'],
  'title': u'To induce or not to induce: do patients at greatest risk for fatal rejection benefit from cytolytic induction therapy?',
  'url': [u'http://www.sciencedirect.com/science/article/pii/S1053249804000348']},
 {'authors': '',
  'citation-text': u'Cited by 24',
  'citation-url': [u'/scholar?cites=17124140059467239571&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  9). These data provide the  CTR  degradation curves used to  estimate CTR  degradation in Step C. There are several test protocol issues that must be addressed  when performing optocoupler  CTR  degradation measurements.  ...',
  'journal-year-src': u'R Reed, C Poivey, PW Marshall, K LaBel\u2026 - Nuclear Science, \u2026, 2001 - ieeexplore.ieee.org',
  'related-text': u'nasa.gov ',
  'related-type': u'[PDF]',
  'related-url': [u'http://radhome.gsfc.nasa.gov/radhome/papers/tns2001_Reed.pdf'],
  'title': u'Assessing the impact of the space radiation environment on parametric degradation and single-event transients in optocouplers',
  'url': [u'http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=983196']},
 {'authors': u'K Dembczynski W Kotlowski',
  'citation-text': u'Cited by 49',
  'citation-url': [u'/scholar?cites=7034931432571598998&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  Then, in order to  estimate CTR , we use maximum likelihood estimation (MLE) to learn  all model parameters directly from real historical data.  ...  Moreover, note that such an  estimate  is not equivalent to maximum likelihood  estimate  for the  CTR .  ...',
  'journal-year-src': u',  \u2026 - Workshop on targeting and \u2026, 2008 - cs.put.poznan.pl',
  'related-text': u'put.poznan.pl ',
  'related-type': u'[PDF]',
  'related-url': [u'http://www.cs.put.poznan.pl/dweiss/research/adrules/papers/troa.pdf'],
  'title': u'Predicting ads click-through rate with decision rules',
  'url': [u'http://www.cs.put.poznan.pl/dweiss/research/adrules/papers/troa.pdf']},
 {'authors': u'M Mahdian',
  'citation-text': u'Cited by 28',
  'citation-url': [u'/scholar?cites=763633557854446702&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  the advertiser (the probability that an impression of the ad leads to a click) is  CTR , then the ad  will be shown if bc \xd7  CTR  \u2265 p, and the advertiser will be charged an amount equal to p/ CTR  if a click occurs.4 Intu- itively, this means that assuming that the  estimate CTR  is accurate  ...',
  'journal-year-src': u', K Tomak - Proceedings of the 1st international workshop on \u2026, 2007 - dl.acm.org',
  'related-text': u'tiera.ru ',
  'related-type': u'[PDF]',
  'related-url': [u'http://bib.tiera.ru/b/74964#page=563'],
  'title': u'Pay-per-action model for online advertising',
  'url': [u'http://dl.acm.org/citation.cfm?id=1348600']},
 {'authors': '',
  'citation-text': u'Cited by 70',
  'citation-url': [u'/scholar?cites=8433796124153554749&as_sdt=2005&sciodt=0,5&hl=en'],
  'description': u'...  In this paper, we  estimate CTR  aggregated at 5-minute time intervals. Serving  ...  Regression analysis: To parsimoniously  estimate  TOD variations in article  CTR ,  we perform a regression analysis separately for each bucket. Let  ...',
  'journal-year-src': u'D Agarwal, BC Chen, P Elango - \u2026 of the 18th international conference on \u2026, 2009 - dl.acm.org',
  'related-text': u'eprints.org ',
  'related-type': u'[PDF]',
  'related-url': [u'http://www2009.eprints.org/3/1/p21.pdf'],
  'title': u'Spatio-temporal models for estimating click-through rate',
  'url': [u'http://dl.acm.org/citation.cfm?id=1526713']}]
```
