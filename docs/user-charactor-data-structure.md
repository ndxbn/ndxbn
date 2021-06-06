![data structure diagram](./bO-_IWD14CRxVOefDH0XO6KX4I6bYE03hEV47EmVsPq3q-Ls1SLKDZPf988YGItI20e-pA2Ijt2ZTmhHncvc-Fs6xsjxaeuAhGJbf10wdTOgS3dXyepBSmv37fGSnXmc7AuvJZcUSZZcSCVnYkCjXmSEBnoVkRpdU9A6jBxT36U3IuvFxwF7sSNuTJGLcPBUmwv79umb18LT4W0IUe.png)

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
interface Charactor
class PlayerCharactor implements Charactor
class NonPlayerCharactor implements Charactor
class Retainer extends NonPlayerCharactor

User *--> Account : almost 1 user has only 1 account
Account *--> PlayerCharactor
PlayerCharactor *-> Retainer
@enduml
```
