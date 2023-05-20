Show the provinces that has more patients identified as 'M' than 'F'. 
Must only show full province_name
----------------------------------------------------------------------------------------------------------

SELECT pr.province_name
FROM province_names pr
         JOIN patients p ON pr.province_id = p.province_id
GROUP BY province_name
HAVING SUM(CASE WHEN p.gender = 'M' THEN 1 ELSE 0 END) > SUM(CASE WHEN p.gender = 'F' THEN 1 ELSE 0 END);


With prn as 
(
  select pn.province_name,
  		Sum(p.gender = 'M') male,
  		Sum(p.gender = 'F') female
  from province_names pn
  join patients p on p.province_id= pn.province_id
  Group By province_name 
 )
select province_name
from prn
where male > female
