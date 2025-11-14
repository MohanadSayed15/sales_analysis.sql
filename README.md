# sales_analysis.sql
SELECT B.Region,
       B.Country,
	   S.client_name,
	   SUM(total_revenue) AS 'Total_Revenue' 
FROM dbo.ServicesD AS S
LEFT JOIN dbo.BranchD AS B 
ON B.Branch_ID = S.branch_id
GROUP BY B.Region, B.Country, S.client_name
ORDER BY SUM(total_revenue) DESC
