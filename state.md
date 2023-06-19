# my_learning_teq_reactJS
state : change the anykind of situation
স্টেট হলো কোন কিছুর অবস্থা পরিবর্তন করা।

 - প্রথমে আমাদের import React, {useState} from 'react' ডাটা ইম্পোর্ট করতে হবে।
 - useState() হলো একটা কন্ডিশন
 - [স্টেটের নাম, সেট ফাংশন ], [count, SetCount]
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
 - 

