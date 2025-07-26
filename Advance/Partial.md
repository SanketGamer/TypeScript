Partial-> it makes all properties of a type optional

```bash
interface User{
    name:string,
    age:number,
    gender:string,
    email:string,
}
type UpdateProp=Pick<User,'gender'|'email'>

type UpdatePropsOptional=Partial<UpdateProp>

function updateUsers(updated:UpdatePropsOptional){
  return updated;
}
const inf=updateUser({gender:"male",email:"ssr@123"})
console.log(inf)

```
