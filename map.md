
```
function App() {
  return (
    <div className="App">
      <MovieCounter></MovieCounter>
      <header className="App-header">
      </header>
    </div>
  );
}

function MovieCounter(){
   
const It_product = [ {name: 'Photoshop', year: 1}, {name: 'Illustrator', year: 1.5}, {name: 'Figma', year: 5}, {name: 'XD', year: 12}, {name: 'premiere pro', year: 3}];

  return (
    <div className='App'>
      {
        //nayoks.map(actor => <Nayok name={actor.name} age={actor.age}></Nayok>)
        It_product.map(software => <Software name={software.name} age={software.year}></Software>)
      }
    </div>
    )
  }

  function Software(props){
    const softStyle = {
      border: '5px solid gray',
      color: 'white',
      borderRadius: '10px',
      background: 'black',
      padding: '25px',
      margin: '20px',
    }
    return(
      <div style={softStyle}>
        <h1>Product Name : {props.name}</h1>
        <p4>Licence : {props.age} year</p4>
      </div>
    )
  }
```
Api calling using map
```
function App() {
  return (
    <div className="App">
      <MovieCounter></MovieCounter>
      <header className="App-header">
      </header>
    </div>
  );
}

function MovieCounter(){

  const[users, setUser] = useState([]);

  useEffect(()=>{
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(res=>res.json())
    .then(data => setUser(data))
  }, [])

  return (
    <div className='App'>
    
    information : 
    {
        users.map(info => <li> id : {info.id} <br></br> name : {info.name}</li>)
    }
  
    </div>
    )
  }
```
