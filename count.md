method-1
```
const [count, setCount] = useState(0)

<div className="card">
    <button onClick={() => setCount((count) => count + 1)}>
      count is {count}
    </button>
</div>
```

method-2
```
state = {
  count : 0
}
incrementCount = () =>{
    this.setState({second : this.state.count + 1})
}

<span className='Text'>S : {this.state.count}</span>
 <button className='Btn' onClick={this.incrementCount}>+</button>
```
