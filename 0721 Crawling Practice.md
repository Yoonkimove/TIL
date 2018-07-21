# Crawling practice  

* CSS Selector 이용해서 원하는 문자열 가져오기 - 연습  

```
from urllib import request
from bs4 import BeautifulSoup

url = "https://www.centennialcollege.ca/programs-courses/full-time/software-engineering-technology-coop/"
with request.urlopen(url) as f:
  html = f.read().decode('utf-8')
```

```
bs = BeautifulSoup(html, 'html5lib')  # 내부에서 html5lib로 DOM을 만듦
title_elements = bs.select('div#programsOverviewAcc table.tbl.responsive tbody tr td')
titles = [e.text for e in title_elements]
titles
```

```
centennial = bs.select('div#programsOverviewAcc table.tbl.responsive tbody tr')
titles = []
for subject in centennial:
  # "td:nth-of-type(2)"은 tr의 자식 중 두번째 td 엘리먼트를 찾아줍니다.
  title = subject.select_one('td:nth-of-type(2)')
  titles.append(title.text)
titles
```

```
centennial = bs.select('div#programsOverviewAcc table.tbl.responsive tbody tr')
titles = [s.select_one('td:nth-of-type(2)').text for s in centennial]
titles
```

