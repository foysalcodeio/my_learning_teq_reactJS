# my_learning_teq_reactJS
state : change the anykind of situation
স্টেট হলো কোন কিছুর অবস্থা পরিবর্তন করা।
কোথায় ব্যবহৃত হয় ? 
যে কোন ডাটা অথবা ডিজিট বাড়ানো অথবা কমানো জন্য স্টেট ব্যবহৃত হয়। যদি আমরা উদাহরন হিসাবে একটা ওয়েব-এ্যাপ্লিকেশন এর ‍শপিং চার্টকে ধরে নিতে পারি।


 - প্রথমে আমাদের import React, {useState} from 'react' ডাটা ইম্পোর্ট করতে হবে।
 - useState() হলো একটা কন্ডিশন
 - [স্টেটের নাম, সেট ফাংশন ], [count, SetCount]
 - মানে কাউন্ট এর মান হচ্ছে useState(10);
 - setCount মানে উদাহরনসরুপ একটা জারের মত। যার মধ্যে ডাটা অথবা ভ্যালু রাখা হয়
 
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
 

 

