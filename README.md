# bav_biblissima_ids

SPARQL query #1:
```
SELECT ?entity ?shelfmark ?id_bbma ?portal_url
WHERE
{
  ?entity wdt:P194 wd:Q32956 ;
          wdt:P195 ?shelfmark .
  OPTIONAL { 
    ?entity wdt:P129 ?id_bbma 
    BIND(CONCAT('https://portail.biblissima.fr/ark:/43093/', ?id_bbma) AS ?portal_url).
  }
```

SPARQL query #2:
```
SELECT ?entity ?shelfmark ?id_bbma ?portal_url
WHERE
{
  ?entity wdt:P194 wd:Q32956 ;
          wdt:P195 ?shelfmark .
  FILTER regex(?shelfmark , "^{shelfmark_label_here}$", "i")
  OPTIONAL { 
    ?entity wdt:P129 ?id_bbma 
    BIND(CONCAT('https://portail.biblissima.fr/ark:/43093/', ?id_bbma) AS ?portal_url).
  }
}
```
