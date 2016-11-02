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
##
