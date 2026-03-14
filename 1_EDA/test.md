# Heading 1
## Heading 2
### Heading 3

Normal Text  
**bold**  
*italic*  
`This is code`
- Bullet 1  

1. number

[LINK TEXT](https://google.com)

![ALT TEXT](https://github.com/lukebarousse/SQL_Data_Engineering_Course/raw/main/Resources/images/1_1_Project1_EDA.png)

![Project 1 Overview](../Images\1_1_Project1_EDA.png)

```sql
SELECT
    sd.skills, 
    COUNT(jpf.*) AS demand_count
FROM job_postings_fact AS jpf
INNER JOIN skills_job_dim AS sjd 
    ON jpf.job_id = sjd.job_id
INNER JOIN skills_dim AS sd
    ON sjd.skill_id = sd.skill_id
WHERE 
    jpf.job_title_short = 'Data Engineer'
    AND jpf.job_work_from_home = TRUE
GROUP BY 
    sd.skills
ORDER BY 
    demand_count DESC
LIMIT 10;
```

