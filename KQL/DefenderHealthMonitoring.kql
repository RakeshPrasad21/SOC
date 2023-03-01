DeviceInfo 
| summarize arg_max(TimeGenerated,*) by DeviceId
| extend ParsedFields=parse_json(LoggedOnUsers)[0]
| extend DurationAtLeast= format_timespan(now()-TimeGenerated,'dd:hh:mm:ss')
| project DurationAtLeast,TimeGenerated,DeviceName,DomainName=ParsedFields.DomainName,UserName=ParsedFields.UserName
| order by DurationAtLeast asc
