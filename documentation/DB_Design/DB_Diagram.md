~~~plantuml

@startuml DB_Diagram

' hide the spot
hide circle

' avoid problems with angled crows feet
skinparam linetype ortho

entity "Shooter" as e01 {
  *e1_id : number <<generated>>
  --
  *First_Name : text
  *Last_Name : text
  *Status : text
  description : text
  is_coach : number
}

entity "Shooter_Pins" as e04 {
  *e4_id : number <<generated>>
  --
  *e1_id : neumber <<FK>>
  *1e_id : neumber <<FK>>
  description : text
  
}

entity "Pins" as e05 {
  *e5_id : number <<generated>>
  --
  *Pin_Name : text
  description : text
}


entity "Equipment" as e03 {
  *e3_id : number <<generated>>
  --
  Equipment_Type : text
  Equipment_Manufacturer : text

  other_details : text
}


entity "Equipment_list" as e06 {
  *e6_id : number <<generated>>
  --

  *e1_id : neumber <<FK>>
  *e3_id : neumber <<FK>>
  Equipment_Type : text
  Equipment_Manufacturer : text

  other_details : text
}


e01 ||..o{ e04
e04 }o..o| e05
e06 ||..o{ e03
e01 ||..|| e06



@enduml

~~~