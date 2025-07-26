
```bash

Readonly->it lets u do inforce internal value of obj not allow to change

in there allowd to change the internal value of user but it not allow to chnage the reff but how how i stop to access the internal value.
type User={
    name:string,
    age:number
}
//now i can not change the value
const user:Readonly<User>={
    name:"hhh",
    age:22
}

user.name="swde"
console.log(user.name)
```
Record
```bash
 type User={
     id:string,
     username:string
 }
this not the cleaner way

type Users={
 [key:string]:User
 }

 type Users=Record<number,string>
 2nd one is more cleaner than 1st 
const users={
    "r@123":{
        id:1,
       username:"hhh"
   },
   "ras1dr@":{
        id:2,
        username:"rrr"
  }
 }
```
Map: easier syntax to access key value pairs
```bash
const users=new Map()
users.set("r@123",{id:1,username:"hhh" })
 users.set("ras1dr@",{id:2,username:"rrr"})

 const user=users.get("r@123")
 console.log(user)
```

Exclude-> it lets u doing exclude the specific members from the value
```bash
 type EventType = 'click' | 'scroll' | 'mousemove';
 type ExcludeEvent = Exclude<EventType, 'scroll'>; // 'click' | 'mousemove'

 const handleEvent = (event: ExcludeEvent) => {
   console.log(`Handling event: ${event}`);
 };

 handleEvent('click'); // OK
```
