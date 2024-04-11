# Flower Issues
 
This repository is used with the sole purpose of tracking Flower Client issues and new requests/suggestions.
 
To open a new issue use the **Issues** section on Github.



Libreria per la visualizzazione del flower nel progetto, basato sugli elements generati dal builder

## Setup rapido Redux toolkit
```js

import { combineReducersWithFlower, flowerEnhancer } from '@stackhouseos/flower-client'

const store = configureStore({
  reducer: combineReducersWithFlower({...reducersList}),
  enhancers: [flowerEnhancer()],
})

```


### Con sagas custom

```js
import { combineReducersWithFlower, flowerEnhancer } from '@stackhouseos/flower-client'

const store = configureStore({
  reducer: combineReducersWithFlower({...reducersList}),
  enhancers: [flowerEnhancer([appSaga()])],
})

```


## Setup su progetto esistente
Integrazione su redux e redux-saga già configurati nel progetto

Aggiungi ai tuoi reducer il flower

```js

import { flowerReducer } from '@stackhouseos/flower-client'

export default combineReducers({
  flower: flowerReducer,
  ...reducers
})

```

Aggiungi alle tue saghe
```js

import { flowerSaga } from '@stackhouseos/flower-client'

export default function* root() {
  yield all(
    [
      flowerSaga(),
      ...sagas
    ]
  )
}

```

## Esempio

```js

import Flower from '@stackhouseos/flower-client'

<Flower 
  elements={[/*elements from flower builder*/]} 
  name={'login'} 
  reducerName={`users`}
 />

```


<!-- react-components-docs -->
[CurrentNode.js](src/components/CurrentNode.js)
### 

#### Props

##### flowName

- **required:** true
- **type:** string 



##### reducerName

- **required:** false
- **type:** string 



##### prefix

- **required:** true
- **type:** string 



##### parentFlow

- **required:** false
- **type:** string 




[Flower.js](src/components/Flower.js)
### FlowerClient

#### Props

##### elements

- **required:** false
- **type:** instanceOf 

Elementi come da export del builder.

##### name

- **required:** false
- **type:** string 

Nome del flower, es. login

##### startId

- **required:** false
- **type:** string 

Nome del flower, es. login

##### reducerName

- **required:** false
- **type:** string 

Nome del nodo di partenza

##### parentFlow

- **required:** false
- **type:** string 

Nome flower che contiene questo flower,

##### reloadKey

- **required:** false
- **type:** any 



##### extraContext

- **required:** false
- **type:** instanceOf 



##### destroyOnUnmount

- **required:** false
- **type:** bool 


<!-- react-components-docs:end -->
