# OOAD-WEEK11
##State Diagram
###1 
```

@startuml
scale 600 width
[*] -> User 
User --> TicketMachine : ChooseStation
User --> TicketMachine : InsertMoney 
TicketMachine --> Display : Showcost
TicketMachine --> TicketMachine : checkMoney 
TicketMachine --> User : printTicket
User --> [*] : printTicket
User --> [*] : returnmoney
@enduml
```
<img src = "https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.1.png?raw=true">

###2
```

@startuml
scale 600 width
[*] -> user 
user -> CoinCounting : InsertCoin()
CoinCounting ->user : returncoin()
CoinCounting -> WashingMachine : Start()
WashingMachine  -down-> user : ShowTime
WashingMachine -> user : returnclothes
user --> [*] : returnclothes
user --> [*] : returncoin()
@enduml 
```
<img src = "https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.2.png?raw=true">
###3
```@startuml

[*] -> user 
user  -down-> MachineCheckIDCar : StartUseTollway
user -down-> MachineCheckIDCar : EndUsetollway
MachineCheckIDCar -> database : Distance Calculator
database -> MachineCheckIDCar : senttotalcharges
Display -> user : showtotalcharges
database -> cuttingFundSystem : cuttingfund
MachineCheckIDCar -down-> Display : totalcharges
@enduml 

```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.3.png?raw=true">
###4
``` @startuml
[*] -> User 
database -> bank : senttotalcharges
bank -down-> banksystem : checkmoneyfromaccount
banksystem -up-> User : SentSMSDon'tHasMoney
banksystem -up->bank : cutmoneyfromaccount
banksystem -up-> User : SentSMS
User -> [*] : SentSMS
@enduml
```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.4.png?raw=true">
###5
```@startuml
[*] -> user 
user -up-> LoginPage : InsertNameAndPass
LoginPage -> WebDatabase : CheckNameandPass
WebDatabase -down-> user : SHowIncorrect
WebDatabase -down-> user : enterpage
user -> [*] : enterpage
user -> [*] : SHowIncorrect
@enduml
```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.5.png?raw=true">
##Activity Diagram
###1
```@startuml

(*) -> User 

User --> TicketMachine 
TicketMachine --> Display : Showcost
if "checkMoney" then 
-->[true] "printTicket"
         -right-> (*)
else 
->[false] "returnmoney"
      --> (*)

@enduml
```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.6.png?raw=true">
###2
```
@startuml
scale 600 width
(*)-> user 
user -> CoinCounting : InsertCoin()
if "money=20" then 
-->[true] "WashingMachine:Start"
  --> returnclothes
  -->(*)
 else
 ->[false]"returncoin"
-->(*)

@enduml 

```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.7.png?raw=true">
###3
```
@startuml

(*) -> user 
user  -down-> MachineCheckIDCar 

MachineCheckIDCar -> database 
database -> Display
Display -> user 
database -> cuttingFundSystem 
if "money>totalcharges" then 
-->[true] "cuttingMonney"
  --> sentSMS
  -->(*)
 else
 ->[false]"Can'tcuttingMonney"
 --> sentSMS
-->(*)

@enduml 
```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.8.png?raw=true">
###4
```

 @startuml
(*) -> User 
User-> bank 
bank -down-> banksystem
if "money>totalcharges" then 
-->[true] "cuttingMonney"
  --> sentSMS
  -->(*)
 else
 ->[false]"Can'tcuttingMonney"
 --> sentSMS
-->(*)

@enduml
```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.9.png?raw=true">
###5
```@startuml
(*) -> user 
user -down-> LoginPage 
LoginPage -down-> WebDatabase 
if "CheckNameandPass" then 
-->[true] "enterpage"

  -->(*)
 else
 ->[false]"SHowIncorrect"
-->(*)

@enduml
```
<img src ="https://github.com/Hathaichanok241/OOAD-WEEK11/blob/master/homework/11.10.png?raw=true">
