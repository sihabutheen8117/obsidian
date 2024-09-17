### Routes in Next (file based)

- every folder under the app or src/app will be treated as the routes .if that folder has the page file and page file class must be export default.
- if we dont want make the folder as routes we can do that by route grouping concept.

##### Route Grouping
- name the like this (name) , inside the braces . then this folder will not be see route , 
- the folder inside that folder can directly call. as route without parent
- like localhost/child instead of localhost/name/child.

### Client side navigation
```
import {Link} from "next/link"

// inside your class or default export function

<Link href="/" > Home </Link>

```

##### Active link
- styling the active link.
