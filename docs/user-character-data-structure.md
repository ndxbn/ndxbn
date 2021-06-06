![data structure diagram](./bO-zIaD148NxVOefLOXWQn4YzYA23p1U9-R2_iZkB9XETmK5Uviq4a4HKOiqWe8FCwZaBTnBhX6YZTsStUyRvgXUOFGSZLPSioQGD9PqB-b6yaJokQHJIG-IhoNVINgIz2RvLKuU9P-LeSIFsulfyPNaby_Hy_Ho_3wQg4fZ2B0Ro2lhc41JdnK0mY0QjB3aV9dt72yhillG8AsoKLKkMf.png)

FF14 の場合のデータ構造だけれど、おそらく他のネトゲなどにも適用できる構造だと思う。

```puml
@startuml
title アカウントやキャラクターのデータ構造・相関図
class User
note left
  a human (or a bot)
end note
class Account
note bottom
  use to login.
end note
interface Character
class PlayerCharacter implements Character
class NonPlayerCharacter implements Character
class Retainer extends NonPlayerCharacter

User *--> Account : almost 1 user has only 1 account
Account *--> PlayerCharacter
PlayerCharacter *-> Retainer
@enduml
```
