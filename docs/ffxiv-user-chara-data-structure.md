```puml
@startuml
title FF14 における、アカウントやキャラクターのデータ構造・相関図
class User
note left
  a human (or a bot)
end note
class Account
note bottom
  use to login.
end note
interface Charactor
class PlayerCharactor implements Charactor
class NonPlayerCharactor implements Charactor
class Retainer extends NonPlayerCharactor

User *--> Account : almost 1 user has only 1 account
Account *--> PlayerCharactor
PlayerCharactor *-> Retainer
@enduml
```
