#### installing react redux

```
npm install @reduxjs/toolkit react-redux
```

- create src - app -store.js
- use single store to manage all the things

#### Step 1

in store.js
```
import { configureStore } from '@reduxjs/toolkit'


export const store = configureStore ({
	reducer : {
	
	}
})

```

#### Step 2

- in app component or index.js

```

import store from 'src/app/store'
import {Provider} from 'react-redux'




```