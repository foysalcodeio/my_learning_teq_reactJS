# my_learning_teq_reactJS


 - প্রথমে আমাদের import React, {useState} from 'react' ডাটা ইম্পোর্ট করতে হবে।
 - useState() হলো একটা কন্ডিশন
 - [স্টেটের নাম, সেট ফাংশন ], [count, SetCount]
 - মানে কাউন্ট এর মান হচ্ছে useState(10);
 - setCount মানে উদাহরনসরুপ একটা জারের মত। যার মধ্যে ডাটা অথবা ভ্যালু রাখা হয়

সিম্পল উদাহরন-1
```
function FavoriteColor() {
  const [color, setColor] = useState("red");
  return (
    <>
      <h1>My favorite color is {color}!</h1>
      <button
        type="button"
        onClick={() => setColor("blue")}
      >Blue</button>
    </>
  )
}
```
useState() নিয়ে বেসিক কনসেপ্ট 
```
function MovieCounter(){
  
  // const res = useState(5) 
  // console.log(res)       

  //step - 1
  // const result = ['abc', 'def']
  // console.log([result[0], result[1]])

  //step - 2 if I used distructure
  //const [first, second] = ['abc', 'def']
  //console.log(first, second)

  // const [first, second] = useState(0)
  // console.log(first, second)

  const [count, setCount] = useState(5) // first : set, second: update
  console.log(count, setCount)


  
  return (
    <div>
      <button>Add Movie</button>
      <h3>number of movie : </h3>
    </div>
  )
}

```

ভিন্ন ভাবে যদি চিন্তা করি তাহলে অনেকটা এইরকম হয় - color = red [setcolor]
 
 সিম্পল ‍state কোড
 ```
 function Counter(){
  const [count, setCount] = useState(10);
  return(
    <div>
      <h1>counter : {count}</h1>
    </div>
  )
} 
 ```
 
 স্টেপ - 1
 ```
 function Counter(){
  const [count, setCount] = useState(10);
  const handleIncrease = () => console.log('clicked');
  return(
    <div>
      <h1>counter : {count}</h1>
      <button onClick={handleIncrease}>Increase</button>
    </div>
  )
}
 ```
স্টেপ - 2
ফাইনাল স্টেপ
 ```
 function Counter(){
  const [count, setCount] = useState(10);
  const handleIncrease = () => {
    const newCount = count + 1;
    setCount(newCount);
  };
  return(
    <div>
      <h1>counter : {count}</h1>
      <button onClick={handleIncrease}>Increase</button>
    </div>
  )
}
 ```
স্টেপ - 3
ডাটা বাড়ানো এবং কমানো
 ```
 function Counter(){
  const [count, SetCount] = useState(0);
  const handleIncrease = () => {
    const NewCount = count + 1
    SetCount(NewCount);
  };
  const handleDescrease = () => {
    const newCount = count - 1
    SetCount(newCount)
  }

  return(
    <div>
      <h2>Counter : {count}</h2>
      <button onClick = { handleIncrease} >increase</button>
      <button onClick = { handleDescrease } >Des-crease</button>
    </div>
  )
 ```
 সর্টকাট করা যায় এভাবে
 ```
 function Counter(){
  const [count, SetCount] = useState(0);
  const handleIncrease = () =>  SetCount(count + 1);
  return(
    <div>
      <h2>Counter : {count}</h2>
      <button onMouseMove = { () => SetCount(count + 1) } >Increase</button>
      <button onClick = { () => SetCount(count - 1) } >Des-crease</button>
    </div>
  )
}
```



