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
- set provider 

```

import store from 'src/app/store'
import {Provider} from 'react-redux'


reactDOM.render(

	<Provider store={store}>
		<App/>
	</Provider>
	
)

```


#### Step 3

- create a feature dir inside the src.
- inside this fe dir we can create many features we want.
- for example we create counter.
- inside the counter , we create a Slice for a counter.
- create counterSlice.js
- inside this
```

import {createSlice} from '@reduxjs/toolkit'

const initialState = {
	 count  = 0;
}

export const counterSlice = createSlice({
	name : 'counter',
	intialState,
	reducer:{
		//inside the reducer
		increment : (state) => {
			state.count += 1 ;
		} 

		howmuch : (state ,action) => {
			state.count += action.payload
		}
	}
})

export const { increment ,howmuch } = counterSlice.action ;
export defualt counterSlice.reducer ;
```
- inside the reducer : you can create many number of action that you wants do with counter. through this you can modify the counter state.
- what is payload : payload is used to get the value which passed in the dispatcher.

#### Step 4
- add your slice to the configuration.
- first you need to import your slice

- inside the store.js
```
import { configureStore } from '@reduxjs/toolkit'
import counterReducer from '../features/counter/counterSlice'

export const store = configureStore ({
	reducer : {
	
		//here you can add your reducer

		counter : counterReducer,
	}
})
```



### How to use

- inside your component
```

	import {useSelector ,useDispatch } from 'react-redux'
	import  {increment ,howmuch } from 'location'


const Counter = () => {

	const count = useSelector( (state) => state.counter.count )
	const dispatch = useDispatch() ;

	return(
		<>
		{count}

		<button onClick={() => dispatch(increment())}> + </button>
		<button onClick={()=> dispatch(howmuch(5))}> +5  </button>
		</>
	)
}
```


next -> [[Structure and DataFlow - react-Redux]]