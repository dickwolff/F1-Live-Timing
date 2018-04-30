Given the  [following](https://www.formula1.com/sp/static/f1/2018/live/Baku/Practice2/all.js) data source.

## Introduction
There are different datasources that are being transmitted through the response data. These are transmitted in format: `SP._input'{type}',{JSON formatted CSV data}');`. One or more of the datasources can be sent in one message.

| Type | Definition |
| :--- | :--- |
| `sq` | _Unknown_ |
| `cpd` | _Unknown_ |
| `b` | Driver best times |
| `o` | Driver times |
| `x` | _Unknown_ |
| `c` | Commentary in English, German and French |
| `init` | Containing data about which drivers are to drive and which team they drive for |
| `au` | _Unknown_ |
| `cp` | _Unknown_ |
| `f` | _Unknown_ |
| `positioning` | _Unknown_ |

## Correlating data to drivers
Intially the driver data is sent using datasource type `init`. Following this initial push, driver data is correlated by order. So when `init` pushes drivers in the order `VAN, RIC, VET`, any other datasource containing data that is driver related will push them in the same order. So when datasource `o` pushes sector times, the first index belongs to driver `VAN`, the second to driver `RIC`, etc.

## Datasource type `o`

```
Data for driver 2 VAN (#19 in results)

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

## Datasource type `b`

Another format in which driver data is presented. Presumably this is represents the fastest times:
```
Data for driver 3 RIC (#1 in results)

{
  "B": ",102.795,16,1,36.311,-1,3,41.33,-1,1,24.841,-1,1,219,,14,234,,9,347,,1,323,,6,,,,"
}
```

Legend to this data source:

| Number | Data |
| :--- | --- |
| 0 (?) | _Unknown_ |
| 1 (102.795) | Total lap time |
| 2 (16) | _Unknown_ |
| 3 (1) | Position on leaderboard |
| 4 (36.311) | Sector 1 time |
| 5 (-1) | _Unknown_  |
| 6 (3) | Position on sector 1 leaderboard |
| 7 (41.33) | Sector 2 time |
| 8 (-1) | _Unknown_ |
| 9 (1) | Position on sector 2 leaderboard |
| 10 (24.841) | Sector 3 time |
| 11 (-1) | _Unknown_ |
| 12 (1) | Position on sector 3 leaderboard |
| 13 (219) | _Unknown_ |
| 14 (?) | _Unknown_ |
| 15 (14) | _Unknown_  |
| 16 (234) | _Unknown_ |
| 17 (?) | _Unknown_ |
| 18 (9) | _Unknown_ |
| 19 (347) | _Unknown_ |
| 20 (?) | _Unknown_ |
| 21 (1) | _Unknown_ |
| 22 (323) | _Unknown_ |
| 23 (?) | _Unknown_ |
| 24 (6) | _Unknown_ |
| 25 (?) | _Unknown_ |
| 26 (?) | _Unknown_ |
| 27 (?) | _Unknown_ |
| 28 (?) | _Unknown_ |

------------------

## Datasource type `g`

Datasource for tyre information:
```
Data for driver 7 RAI (#2 in results)

{
  "G": "33,0.069,,,"
}
```

Legend to this data source:

| Number | Data |
| :--- | --- |
| 0 (33) | Number of laps driven |
| 1 (0.069) | Gap to leader (on same tyre?) |
| 2 (?) | _Unknown_? |
| 3 (?) | _Unknown_ |
| 4 (?) | _Unknown_  |
