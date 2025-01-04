# DashboardCreation
Elastic Dashboard Creation


**Failed Login Attempts**

1. Delete existing dashboards
2. Click create dashboard
3. Click create visualization
4. Enter "last 15 years" for time range.
5. Add Filter date for "failed logon attempts" - IDs that match **4625** = Failed logon attempt on a Windows system. Field = event.code, Operator = is, and Value = 4625
6. Specify "Windows" as the Index pattern
7. For the visualization type, use a table.
8. Create a row. select a field = user.name.keyword, number of values = 1000, ranked by = count of records.
9. Add metrics, function = count, (The count of records will be the data, assuming that data will be preset).
10. Create another row as "host.hostname.keyword" (which represents the computer reporting the failed logon attempt.)
11. Create another row for "logon type". Using the "winlog.logon.type.keyword", (Used to display the type of method used to logon - either network or service.
12. Save and return the dashboard. Name "No title" the table and also the dashboard.
13. To reopen dashboard, click the listed dashboard and then click on the gear - select edit icon to be taken to the full saved dashboard. 

    **Usernames can be excluded by specifying additional filters ex. field = user.name.keyword, operator = is not, value = "username to be excluded".**
    **Computer accounts can be excluded by specifying the following KQL query and clicking on the "Update" button.

      **SIEM Visualization Example 1: Failed Logon Attempts (All Users)**
      NOT user.name: *$ AND winlog.channel.keyword: Security
      The AND winlog.channel.keyword: Security part is to ensure that no unrelated logs are accounted for.
    

    
