
to implement programmatic routing or navigating we need a useRouter

```
"use client"

import {useRouter} from "next/navigation"

const router = useRouter()

//after this we can navigate for example

router.push("/")
```
- it will go to the "/" when it invoke.
- it will work in client side , so we need to specify "use client"