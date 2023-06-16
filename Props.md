# my_learning_teq_reactJS
#  কম্পোনেন্ট এবং প্রপস

## প্রপস : এটা সাধারনত ডায়নাম্যাকালি ভ্যারিয়াবলের ইনপুটের কাজে ব্যবহত হয়।

Props useally transfer the data or send the data one component to another component. 
 
 এটার সুবিধা হল নিদিষ্ট একটি ফাংশন তৈরী করে সবকাজ একসাথে কম সময়ে এবং ইফিসিয়েন্ট কাজ করা হয়। ওই ফাংশনকে এইচটিএমএল ট্যাগের মত করে ব্যবহার করা যায়।
এইটা হল ‍app.js এর রুট সেকসন। সর্বপ্রথম এখানে কাজ শুরু করতে হয়।
```
import React from 'react';
class App extends React.Component {
  render() {
    return (
      <div>
        
      </div>
    );
  }
}
export default App;
```
বাহিরের থেকে কোন ডাটা ইমপোর্ট করতে হলে তা সর্বপ্রথম classprops.js নামে ফাইল তৈরী করতে হয় এবং 
```
import React, { Component } from "react";
```
লিখে তা সংযুক্ত করতে হয়। সবার শেষে সেই ফাইলটাকে div এর মধ্যে  <Classprops/> এ্যাড করে এক্সপোর্ট করতে হয়।

```
export default Classprops;
```

কম্পেনেন্ট 2 প্রকার। 1. ক্লাস কম্পোনেন্ট 2. ফাংশনাল কম্পোনেন্ট
1. ক্লাস কম্পোনেন্ট : এটা this কিওয়ার্ড ব্যবহৃত হয়। এটা ফাংশন ডিক্লারশন export class Classprops extends Component দিতে হয়। এটার স্ট্রাকচার হল
```
import React, { Component } from "react";
export class Classprops extends Component {
    render(){
        return(
            <div>
                <h1>Hello, {this.props.name} from {this.props.place} | This is class props </h1>
                <p>{ this.props.children }</p>
            </div>
        )
    }
}
```
2. ফাংশন কম্পোনেন্ট : এখেত্রে this কিওয়ার্ড ব্যবহত হয় না এবং render ফাংশন ব্যবহৃত হয় না। এটার স্ট্রাকচার হল -
```
import React from 'react';
function Functionprops(props){
    return(
        <div>
            <h3>This is Function Component</h3>
            <h3>Hello {props.name} from {props.place}, I am Function</h3>
        </div>
    )
}
```

# উচ্চতর ডিক্লারাশন
নিচের ফাংশনটা সাধারন props ডিক্লারেশন করা হয়েছে। যদি আমরা চাই 2য় কোডটা র্কালি ব্র্যাকেট ব্যবহার এ্যাডভান্স করতে পারি
```
function Product(props) {
    return (
        <div>
            <h1>List : </h1>
            <p>Name : {props.name}</p>
            <p>Description : {props.description}</p>
            <p>Price : {props.price}</p>
        </div>
    )
}
```
পার্ট-2
```
function Product({name, description, price}) { 
    return (
        <div>
            <h1>List : </h1>
            <p>Name : {name}</p>
            <p>Description : {description}</p>
            <p>Price : {price}</p>
        </div>
    )
}
```



