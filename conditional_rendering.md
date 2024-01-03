```
import { useEffect, useState } from 'react'
import './App.css'


function App() { 

  const [color, setColor] = useState("red")

  const handleColor = () => {
    setColor("blue")
  }

  return (
    <>
      <div>
        <p>color : {color}</p>
        <button onClick={ () => handleColor()}>Click</button>
        {color === 'red' ? <h1>This is red color </h1> : <h1>This is blue color</h1>}
      </div>
    </>
  )
}

export default App
```
