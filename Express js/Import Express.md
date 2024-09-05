
```
import express from "express";

const app = express();

const PORT = process.env.PORT || 3000;

app.listen(PORT ,()=>{
	console.log(`Running on port ${PORT}`)
})

```

- app.listen(port ,()) : this means it listen the incomming req from this port and return the function