# Prompt for extracting date and time from non-standard text

### Date/time handling has always been messy in code, so this prompt allows to extract freeform dates and turning them into structured JSON.


```
Extract all temporal expressions from the text, including partial, informal, or business-context 
information. 
Return them in JSON format as an array of objects: [{"type": "TYPE", "value" : EXTRACTED VALUE", "timezone" "TIMEZONE_IF_SPECIFIED"}]

Types can be: 
- specific_date: Full or partial dates (e g. , '12/25/2024' , 'December 25th", "the 25th , '25/12')
- relative_day: Relative references (e.g., "tomorrow", "day after tomorrow", "next week", "in a few days" ) 
- weekday: Day mentions (e.g., "this coming Monday" , "Monday" "next Tuesday" , "every Friday" , 
- month: Month references (e.g., "in March", "next month", "end of April", "early next month") 
- time: Time mentions (e.g., "at 2pm PST", "morning EST", "afternoon GMT", "first thing , "COB", "EOD") 
- duration: Duration mentions (e.g., "for 2 hours", "30 minutes", "couple of hours", "brief", "quick") 
- period: Time periods (e.g., "this week", "next quarter", "holiday season", "fiscal year", "In couple of hours" 
- preference: Time preferences (e.g., "whenever works", "at your convenience", "when you' re free", "now", "ASAP") 
- recurring: Recurring patterns (e.g., "every other week", "daily" , "weekly" , "monthly" )
- fiscal: Fiscal year references (e.g., Q2 FY25", "FY24" , "fiscal year end" ) 
- cultural: Cultural or seasonal references (e.g., "during Ramadan", "before Christmas", "summer break", "after holidays") 
- milestone: Project-specific milestones (e.g., "after launch", "post-review", "before deployment") 
- business: Business process references (e.g., "after standup", "next sprint", "post-refinement") 

Rules: 
1. Preserve original wording in the 'value' field but convert it to lowercase (retain qualifiers like "early" "late" "every", or "next"). 
2. If multiple temporal expressions are found, return each one as a separate object in the array. 
3. Include timezone in the response when specified (e.g. , "PST", "EST", "GMT", "1ST"). 
4. Distinguish between fiscal and calendar year references. 
5. Handle cultural and seasonal references with appropriate context. 
6. Recognize project and business process milestones. 
```


