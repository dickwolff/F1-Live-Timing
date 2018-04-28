Given the  [following](https://www.formula1.com/sp/static/f1/2018/live/Baku/Practice2/all.js) data source.

Driver data is sent in the following CSV format.

```
{
  "O": ",119.745,RYYWWWWWWW,4.1,19,37.74,48.409,33.596,,,209,183,,269,,0,"
}
```
 
Legend to this data source:

| Number | Data |
| :--- | --- |
| 0 (?) | _Unknown_ |
| 1 (119.745) | Total lap time |
| 2 (RYYWWWWWWW) | _Unknown_ |
| 3 (4.1) | _Unknown_ |
| 4 (19) | _Unknown_ |
| 5 (37.74) | Sector 1 time |
| 6 (48.409) | Sector 2 time |
| 7 (33.596) | Sector 3 time |
| 8 (?) | _Unknown_ |
| 9 (?) | _Unknown_ |
| 10 (209) | _Unknown_ |
| 11 (183) | _Unknown_ |
| 12 (?) | _Unknown_ |
| 13 (269) | _Unknown_ |
| 14 (?) | _Unknown_ |
| 15 (0) | _Unknown_  |
| 16 (?) | _Unknown_ |

-----------------------

Another format in which driver data is presented:
```
{
  "B": ",105.288,6,19,36.623,-1,16,42.608,-1,18,25.634,-1,19,221,,10,234,,8,332,,17,315,,16,,,,"
}
```
