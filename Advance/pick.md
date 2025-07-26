Pick-> it allows to create new type by selecting a set

in there the problem is if i want to change something again.i have to change inside User and UpdateProps.this is not the right way to access
solution is Pick:
```bash
interface User{
    name:string,
    age:number,
    gender:string,
    email:string,
}

interface UpdateProps{
    gender:string,
    email:string,
}

type UpdateProps=Pick<User,'gender'|'email'>

function updateUser(updated:UpdateProps){
  return updated;
}
const info=updateUser({gender:"male",email:"ssr@123"})
console.log(info)
```
