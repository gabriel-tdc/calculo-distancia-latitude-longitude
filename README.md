# calculo-distancia-latitude-longitude
Calcular a distancia entre dois pontos, pela LATITUDE e LONGITUDE 

```mysql
select (6371 * acos(  
                cos( radians('-23.4957084655761720000000000') )   
              * cos( radians( '-23.5017204284667970000000000' ) )   
              * cos( radians( '-47.4480628967285160000000000' ) - radians('-46.8742790222168000000000000') )   
              + sin( radians('-23.4957084655761720000000000') )   
              * sin( radians( '-23.5017204284667970000000000' ) )   
                ) ) as distance;
```


Ou, utilizando variaveis (PHP) por exemplo:

```
select (6371 * acos( 
                cos( radians('$lat2') ) 
              * cos( radians( '$lat1' ) )  
              * cos( radians( '$long1' ) - radians('$long2') ) 
              + sin( radians('$lat2') ) 
              * sin( radians( '$lat1' ) )
                ) ) as distance;
```
                
*Fonte:*
[Stackoverflow](https://stackoverflow.com/questions/24370975/find-distance-between-two-points-using-latitude-and-longitude-in-mysql#:~:text=SELECT%20getDistance(lat1%2Clng1%2C,lng2)%20as%20distance%20FROM%20your_table.&text=Here's%20a%20MySQL%20function%20that,formula%20to%20calculate%20the%20distance)
