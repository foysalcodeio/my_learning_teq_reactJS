app.js
```
import React, { Component } from 'react'
import './app.style.css'

class App extends Component{
  // constructor(props){
  //   super(props)
  //   this.state = {
  //     count: 0
  //   }
  // }

  state = {
    count: 0
  }

  incrementCount = () =>{
    this.setState({count : this.state.count + 1})
  }
  decrementCount = () => {
    if(this.state.count > 0){
      this.setState({count : this.state.count - 1})
    }
  }

  intervalId = null;

  startTimer = () => {
    if(this.state.count > 0 && !this.intervalId){
      this.intervalId = setInterval(() => {
        this.setState({count : this.state.count - 1},
          ()=> {
            if(this.state.count === 0){
              alert('Timer Finish')
              clearInterval(this.intervalId)
              this.intervalId = null
          }
        })
      }, 1000);
    }
  }

  stopTimer = () => {
    if(this.intervalId){
      clearInterval(this.intervalId)
      this.intervalId=null
    }
  }

  resetTimer = () => {
    this.setState({count:0})
    clearInterval(this.intervalId) // if had a any interval then we clear this
    this.intervalId=null
  }

  render(){
    //console.log(this.count);
    return(
      <div className='App'>
          <h1 className='Heading'> Simple Timer </h1>
          <div className='Container'>
              <button className='Btn' onClick={this.incrementCount}>+</button>
              <span className='Text'>{this.state.count}</span>
              <button className='Btn' onClick={this.decrementCount}>-</button>
          </div>

          <div className='Container'>
              <button onClick={this.startTimer} className='Btn'> Start </button>
              <button onClick={this.stopTimer} className='Btn'> Stop </button>
              <button onClick={this.resetTimer} className='Btn'> Reset </button>
          </div>
      </div>
    );
  }
}

export default App;

```
app.style.css
```
.Heading{
    text-align: center;
    font-weight: 300;
    margin-bottom: 50px;
}
.Container{
    width: 100%;
    text-align: center;
}

.Btn{
    width: 100px;
    margin: 10px 10px;
    padding: 10px 20px;
    border: 1px solid gray;
    color: #222222;
    border: none;
    cursor: pointer;
}
.Btn:hover{
    background-color: rgb(180, 180, 180);
    color: #222222;
}
```
