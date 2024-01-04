
listing process

```

import { useState, useEffect } from 'react';
import axios from 'axios';



const List = () => {
    const [todo, setTodo] = useState([])

    useEffect( ()=> {
      axios.get("https://jsonplaceholder.typicode.com/todos")
        .then((res) => {
          setTodo(res.data)
        })
        .then(data => {
            console.log(data)
        })
    }, [])


    const deleteEvent = (id) =>{
        let deleteId = "Delete ID : " + id;
        alert(deleteId)
        // api call delete

    }


    const editEvent = (id) => {
        let editId = "Edit ID " + id
        alert(editId)
        // api call details
    }


    const detailsEvent = (id) => {
        let detailsId = "Details ID " + id
        alert(detailsId)
        // api call details
    }

    const myList = todo.map((list,i) => {
        return (
            <tr key={list['id']}>

                <td> {list['userId']}</td>
                <td>{list['id']}</td>
                <td>{list['title']}</td>

                <td>
                <button 
                onClick={deleteEvent.bind(this,list['id'])}
                className='btn btn-danger'>
                Delete</button>
                </td>

                <td><button
                onClick={editEvent.bind[this,list['id']]}
                className='btn btn-primary'                
                >Edit</button></td>

                <td><button
                onClick={detailsEvent.bind(this,list['id'])}
                className='btn btn-success'
                >Details</button></td>
            </tr>
        )
    })

    return (
        <div>
            <table className='table table-bordered'>
                <thead>
                    <tr>
                        <th>User Id</th>
                        <th>ID</th>
                        <th>Title</th>
                        <th>Action</th>
                    </tr>
                </thead>

                <tbody>{myList}</tbody>

            </table>            
        </div>
    );
};

export default List;
```
