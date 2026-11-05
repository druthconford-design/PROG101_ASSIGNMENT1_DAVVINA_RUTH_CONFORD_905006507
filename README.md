# PROG101_ASSIGNMENT1_DAVVINA_RUTH_CONFORD_905006507
This is assignment 1 for Programming Logic and Design about The Fair Check System for public transportation in Freetown

## Problem Description
About one million people live in Freetown, and for years they have depended almost completely on informal public transport. The main options are poda-poda minibuses, shared saloon taxis, okada motorcycle taxis and keke three-wheelers. These vehicles are essential, but passengers are often unsure what they should pay. A passenger may be asked for more than the official fare, may not know that the fare has changed, or may simply pay because there is no time to argue at a busy park or on the roadside.

## People affected
The people most affected are daily commuters on low incomes including students, market traders and workers who travel every day. For them even a small extra amount, paid several times a day, adds up over a week. Passengers who are not sure of the correct fare, such as people new to a route, are also more likely to pay too much.

## Why the problem exists
The problem exists for several connected reasons. Fares are agreed between the government and the drivers' union and they change when the price of fuel changes, so the correct amount is not always clear. Most vehicles are privately run and the public sector has found it hard to regulate them. On top of that, a passenger has no quick and neutral way of checking a fare. My proposed solution deals with this last point. It compares the fare the driver asks for with the official fare and tells the passenger clearly whether it is fair.

## Background
Before the reforms that began in 2019, almost all public transport in Freetown was informal. The state bus company, the Sierra Leone Road Transport Corporation, declined because of regulated low fares, rising fuel costs and low productivity, and informal operators filled the gap because the public sector did not have the capacity to regulate supply and enforce licences. A World Bank diagnostic from 2018 estimated that poda-podas carried about 30 percent of passenger demand, shared taxis 27 percent, okadas 20 percent and kekes 15 percent.
Fares also move with fuel prices. In August 2023, after the price of petrol, diesel and kerosene rose from NLe 25.00 to NLe 30.00 per litre, the Ministry of Transport and Aviation and the Motor Drivers Union agreed new public transport fares. A local newspaper reported that commercial vehicles had already raised fares by 50 percent or more after the price increase.
The government has since started to reform the sector. The Sierra Leone Public Transport Authority was created under the Public Transport Act of 2023 to plan, monitor and oversee public transport, and a pilot service of 50 buses started on two corridors. The World Bank itself says there is still a long way to go, so a simple tool that helps passengers check fares is useful alongside these reforms.

## Community Impact
The problem being solved is that passengers cannot easily tell whether the fare they are asked to pay is correct. The expected impact is that a passenger can check a fare in a few seconds, avoid paying more than necessary, and know what to do when a driver asks for too much. Honest drivers also gain, because a clear check reduces arguments over fares.
The main beneficiaries are daily commuters, especially students, market traders and low-income workers. Drivers who charge the correct fare benefit, and so does the transport authority, because the tool supports the fares that have been agreed.
For long-term sustainability the program is deliberately small. It needs no special equipment, and because the passenger enters the official fare from the published list, the program does not go out of date when fares change. Only the tolerance value may need adjusting. Because the design is open, students, councils or NGOs can keep improving it.

## Proposed Solution
FareCheck SL is a simple program that a passenger can run on a phone or computer before paying. The passenger enters the route name, the official fare taken from the published fare list, and the fare the driver is asking for. The program checks that both fares are sensible, works out the difference and the percentage above the official fare, and shows a fare status with advice. The passenger can check another trip straight away, and when finished the program shows how many trips were checked, how many had a fare above the official fare, and the total extra amount that was asked.
There are three fare statuses. FAIR means the driver is asking for the official fare or less, so the passenger should pay and collect any change. SLIGHTLY HIGH means the fare is above the official fare by no more than 10 percent, which could be a problem with change, so the passenger should politely ask for the official fare. OVERCHARGED means the fare is more than 10 percent above the official fare, so the passenger should not pay the extra and should report the vehicle. The 10 percent tolerance and the largest fare accepted (NLe 500) are sample values chosen to show the logic. In real use they would be agreed with the transport authority.

## Computational Thinking Process
I started with decomposition. The big problem of checking a fare was broken into smaller jobs: reading the route and the two fares, checking that the fares are valid, calculating the difference and the percentage, deciding the fare status, choosing the advice, showing the result, and repeating for another trip.
Next I looked for patterns. Every trip check follows the same steps, so the steps can be repeated in a loop. Then I used abstraction to decide what to ignore. Distance, time of day, traffic and the type of vehicle all affect what a trip feels like, but the official fare already takes the route into account, so I kept only the two numbers the passenger can read or hear. Finally I wrote the steps in order, with decisions and a loop, and tested them by working through sample scenarios by hand. 

## Algorithm
Step-by-step algorithm
1.	Start the program.
2.	Set TOLERANCE_PERCENT = 10 and MAX_FARE = 500. Set totalChecks, highFares and totalExtra to 0.
3.	Display the program title.
4.	Read the route name.
5.	Read the official fare and the fare the driver is asking for.
6.	If either fare is 0 or less, or more than MAX_FARE, display an error message and go back to step 5.
7.	Calculate extraAmount = askedFare - officialFare.
8.	Calculate percentOver = (extraAmount / officialFare) x 100.
9.	If askedFare is more than officialFare AND percentOver is more than TOLERANCE_PERCENT, set the status to OVERCHARGED and the advice to "Do not pay more than the official fare. Note the vehicle number and report it to the transport authority."
10.	Otherwise, if askedFare is more than officialFare, set the status to SLIGHTLY HIGH and the advice to "The fare is a little above the official fare. Politely ask the driver or conductor for the official fare."
11.	Otherwise, set the status to FAIR and the advice to "The fare is correct. Pay the fare and collect any change."
12.	Display the route, the two fares, the difference, the percentage, the status and the advice.
13.	Add 1 to totalChecks. If the status is not FAIR, add 1 to highFares and add extraAmount to totalExtra.
14.	Ask "Check another trip? (Y/N)" and read the answer.
15.	If the answer is Y or y, go back to step 4.
16.	Display the number of trips checked, the number of trips above the official fare and the total extra amount asked.
17.	Stop.

## Pseudocode  
 <img width="1248" height="972" alt="pseudocode 1" src="https://github.com/user-attachments/assets/f02fe1c7-0b4e-4696-9529-d3b1aee70e1d" />
 
<img width="1326" height="980" alt="pseudocode 2" src="https://github.com/user-attachments/assets/46bcd87b-0717-4663-9599-c7078ca15771" />

<img width="728" height="242" alt="pseudocode 3" src="https://github.com/user-attachments/assets/33c42881-caae-4992-9546-a741a89b8392" />

## Flowchart
<img width="1220" height="857" alt="Screenshot 2026-11-05 150539" src="https://github.com/user-attachments/assets/0f19f190-a5ec-4591-968b-9e04bcba7170" />

<img width="1277" height="862" alt="Screenshot 2026-11-05 150741" src="https://github.com/user-attachments/assets/f29b00d1-3428-4ff7-93ba-657616c89468" />

<img width="1422" height="857" alt="Screenshot 2026-11-05 150855" src="https://github.com/user-attachments/assets/f646e835-ce00-4519-a326-95ddd08911c3" />

<img width="1462" height="862" alt="Screenshot 2026-11-05 151012" src="https://github.com/user-attachments/assets/0c2c13e1-b627-40e1-8ba2-71591f9c3298" />

<img width="1382" height="857" alt="Screenshot 2026-11-05 151057" src="https://github.com/user-attachments/assets/4afb7efd-95c2-47c5-9952-3ddff0c88615" />

## Author
- Davvina Ruth Conford - 905006507









 
 
 
 
 
