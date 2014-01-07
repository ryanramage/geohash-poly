Transform a geoJSON (Multi)Polygon to a list of geohashes that cover it.

Currently only includes hashes whose centroid falls within the poly itself.
This does not create 100% coverage, but I could consider adding this if there is a need.

Method used is pretty brute-force, but still relatively quick compared to alternative implementations if hash precision is not too granular. Creates an envelope around poly, and iterates over rows and columns, only including hashes that fall in the poly.


```javascript

var polygon = [[[-122.350051, 47.702893 ], [-122.344774, 47.702877 ], [-122.344777, 47.70324 ], [-122.341982, 47.703234 ], [-122.341959, 47.701421 ], [-122.339749, 47.701416 ], [-122.339704, 47.69776 ], [-122.341913, 47.697797 ], [-122.341905, 47.697071 ], [-122.344576, 47.697084 ], [-122.344609, 47.697807 ], [-122.349999, 47.697822 ], [-122.350051, 47.702893 ]]];

var hashList =  geohashpoly(polygon, 7);
```

Results in:
```
[ 'c22zrgg',
  'c22zrgu',
  'c22zrgv',
  'c22zrgy',
  'c22zrgz',
  'c23p25b',
  'c22zrge',
  'c22zrgs',
  'c22zrgt',
  'c22zrgw',
  'c22zrgx',
  'c23p258',
  'c23p259',
  'c23p25d',
  'c22zrg7',
  'c22zrgk',
  'c22zrgm',
  'c22zrgq',
  'c22zrgr',
  'c23p252',
  'c23p253',
  'c23p256',
  'c22zrg5',
  'c22zrgh',
  'c22zrgj',
  'c22zrgn',
  'c22zrgp',
  'c23p250',
  'c23p251',
  'c23p254' ]
```

-------

Some of this was adapted from [geogeometry](http://github.com/jillesvangurp/geogeometry).