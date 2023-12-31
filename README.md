<img width="539" alt="co" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/833cd0f5-3c1e-48af-b327-9fdb8a37f31d">


# INTRODUCTION
Correctional homes, often called correctional facilities or prisons, play a vital role in the criminal justice system. These institutions serve as the primary means of punishment, rehabilitation, and societal reintegration for individuals who have committed offenses. In this case, the analysis was done for minors between the ages of 14 years to 18 years.

### Tools Used: 
Microsoft SQL Server, Tableau

## Key Questions
- What crimes are the most committed
- Which guardian of the juvenile has the most committed crime rate
- Which referral brings in the highest juvenile offenders

## Findings
##### The data set was uploaded into the SQL server for further analysis with the name 'correctional_home'
```
select * from sysobjects where xtype = 'u'
select * from Correctional_home;
```

```
select GENDER, count(GENDER)as 'Count'
from Correctional_home
group By GENDER;
```

- A total number of 412 juveniles were recorded 18 being females and 394 being males.
 
<img width="114" alt="sql 1" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/d728156d-bdb1-4b33-bd17-a66bf35a451e">

```ruby
select Avg(AGE)as 'Avg Age'
from correctional_home;
```

<img width="86" alt="Sql 2" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/f4818365-fc5f-4d33-9ea0-ed4db3b2fdaf">

```
select Count(Distinct NATURE_OF_OFFENCE) as DistinctCount
from correctional_home;
```

<img width="98" alt="Sql 3" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/b5a494e8-ecfa-4eb3-888a-8d14eb9ab60e">

### What crimes are the most committed

```ruby
-- Top 5 cases by Gender
select Top 5 count(NATURE_OF_OFFENCE) as Count_of_offence, GENDER, NATURE_OF_OFFENCE 
from Correctional_home
where GENDER = 'M'
group by GENDER, NATURE_OF_OFFENCE 
order by Count_of_offence Desc;


select Top 5 NATURE_OF_OFFENCE, GENDER, count(NATURE_OF_OFFENCE) as count
from correctional_home
where GENDER = 'F'
group by NATURE_OF_OFFENCE, GENDER
order by count desc;
```

<img width="202" alt="sql 7" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/2eb87d1f-ecf9-4396-8845-b42f15ed38c1">


<img width="253" alt="sql 4" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/b2bec5b9-67b8-41f6-b9cc-694cf5161446">

### Which guardian of the juvenile has the most committed crime rate

```ruby
-- Guardians by cases
select WHO_DID_THE_CHILD_LIVE_PRIOR_TO_INCIDENT, count (NATURE_OF_OFFENCE) as OffenceCount
from Correctional_home
group by WHO_DID_THE_CHILD_LIVE_PRIOR_TO_INCIDENT
order by OffenceCount Desc;
```


<img width="295" alt="sql 5" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/e3aeb7f8-0f4b-4d04-9876-1201b66f5eff">

### Which referral brings in the highest juvenile offenders

```ruby
-- Highest referral 
select Top 5 MODE_OF_REFERRAL, count (MODE_OF_REFERRAL) count
from Correctional_home
group by MODE_OF_REFERRAL
order by count (MODE_OF_REFERRAL)desc;
```

<img width="255" alt="sql 6" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/94301dc0-7c9f-48d9-a9cb-ad84977c42b8">

## Summary 
- Crime conspiracy, theft, culpable homicide, and house trespass are the highest crimes committed by the juveniles
- Juveniles living with their parents commit the most crimes
- referrals are mostly from the court

## Recommendation
- Parents should be made accountable if they are lacking in training, it's ironic that single parents have a lower crime rate
- Juveniles should be spoken to from tender ages on the evils of crimes, in schools, social events even religious gatherings
- Society should be educated on the advantages of these correctional homes, so they can know where to direct each case
- The government should organize conferences, vocational activities, and more engaging and productive activities that will create a good leverage ground for the youths


<img width="802" alt="Correctional Dashboard" src="https://github.com/UkokoD/Correctional-Home-Analysis/assets/135248114/62715e94-0a62-42d7-af12-4ebb813b4301">

















  


  

