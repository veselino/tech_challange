# billups_tech_challange

The database is backed up and uploaded in the .bak file, and can be restored with it from the restore database wizard and using the extracted .bak file in the repo

Since the output can be very large, in case i need to examine those results, i had to save them to a extrenal file from SSMS to open, as XML will not parse that much data (despite chaninging the setting for xml files to unlimited)

the procedure that returns the result is called dbo.poisearch

i used the bellow query to send variables to the SP:

DECLARE @json_data NVARCHAR(MAX)
SET @json_data = '{
 "country" : "US",
 "region": "AZ",
 "city": "Phoenix",
 "radiouskm": "0.4",
 "radiouslat": "33.67246737",
 "radiouslon": "-112.0998372",
 "wktpoly": "POLYGON((-112.108594 33.675704,-112.108585 33.669580,  -112.097808 33.670161, -112.098091 33.676527, -112.108594 33.675704))",
 "poicat": "Lessors of Real Estate",
 "poiname": "Deer Valley II Self Storage"
 }'
EXECUTE dbo.poisearch @json_data


