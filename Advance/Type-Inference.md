Type inference in zod-> U can extract the ts of any schema with (z.infer<typeof mySchema>)
```bash
import { z } from 'zod';
import express from "express";

const app = express();

// Define the schema for profile update
const userProfileSchema = z.object({
  name: z.string().min(1, { message: "Name cannot be empty" }),
  email: z.string().email({ message: "Invalid email format" }),
  age: z.number().min(18, { message: "You must be at least 18 years old" }).optional(),
});
// type finalschema={
//     name:string,
//     email:string,
//     age?:number
// }
type finalschema=z.infer<typeof userProfileSchema>
//both are but 2nd is most optimal way to write code
app.put("/user", (req, res) => {
  const { success } = userProfileSchema.safeParse(req.body);
  const updateBody:finalschema = req.body; // how to assign a type to updateBody?

  if (!success) {
    res.status(411).json({});
    return
  }
  // update database here
  res.json({
    message: "User updated"
  })
});

app.listen(3000)

```
