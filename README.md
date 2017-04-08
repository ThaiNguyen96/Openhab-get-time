# Openhab-get-time
Hi everyone, now I'm trying to get time and display in openhab but I have got this marker and I don't know how to fix this

         rule "Get time"
	when 
	Item Himitsu_Humidity changed or Item Himitsu_Humidity received update
	then
		postUpdate( door_status_time2, new DateTimeType() )
 
		var month  = now.getMonthOfYear
		var day    = now.getDayOfMonth
		var hour   = now.getHourOfDay
		var minute = now.getMinuteOfHour
		door_status_time1.state = month + "-" + day " " + hour + ":" + minute
		door_status_time1.state =  now.toString()
          end	

My items
               String door_status_time1 "Time Last Updated [%s]"
	       
              DateTime door_status_time2 "Time 2 [%1$tA, %1$td.%1$tm.%1$tY %1$tT]"

Sitemaps
              Text item=door_status_time1
	      
              Text item=door_status_time2 

It's maker in line 10 11 12 13
"Multiple markers at this line
- Couldn't resolve reference to JvmIdentifiableElement 'now'.
- Couldn't resolve reference to JvmIdentifiableElement 'getMonthOfYear'."
