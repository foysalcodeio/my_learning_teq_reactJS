class component
```
import React, { Component } from 'react'

export class List extends Component {
    constructor(){
        super();
        this.state={
            color: "red"
        }
    }
  render() {
    return (
      <div>
        <h1>{this.state.color}</h1>
        <button onClick={ () => this.setState({color: "Blue"})}>Blue</button>
        <button onClick={ () => this.setState({color: "green"})}>Green</button>
      </div>
    )
  }
}

export default List

```
DOM ref
```
import React, { Component } from 'react'

export class List extends Component {

    myClick = () => {
        let text = this.myText.value
        alert(text)
    }
  render() {
   return(
    <div>
        <input ref={(input) => {this.myText=input}} className='form-control' type="text" />
        <br />
        <button className='btn btn-primary' onClick={this.myClick}>Submit</button>
    </div>
   )
  }
}

export default List

```
componentdidmount = useEffect
```
import React, { Component } from 'react'
import axios from 'axios';
export class List extends Component {

    constructor(){
        super();
        this.state={
            toDoList: []
        }
    }



    componentDidMount () {
        //api call
        axios.get("https://jsonplaceholder.typicode.com/todos")
            .then((res) => {
                this.setState({toDoList: res.data})
            })
            .catch((err)=>{
                alert(err)
                //edit
                //delete
                //details
            })
    }

    actionClick = (id) => {
        alert(id)
    }

  render() {
    const myList = this.state.toDoList.map((item, i) => {
        return(
            <tr key={item['id']}> 

                <td>{item['userId']}</td>
                <td>{item['id']}</td>
                <td>{item['title']}</td>
                <td><button onClick={this.actionClick.bind(this,item['id'])} className='btn btn-primary'>Action</button></td>
            </tr>
        )
    })
   return(
    <div>
        <table className="table table-hover">
            <tbody>
                {myList}
            </tbody>
        </table>
    </div>
   )
  }
}

export default List

```

