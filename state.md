# my_learning_teq_reactJS
state : change the anykind of situation
স্টেট হলো কোন কিছুর অবস্থা পরিবর্তন করা।

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

