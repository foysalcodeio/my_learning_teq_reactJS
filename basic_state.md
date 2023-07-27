# state
state : স্টেট হলো কম্পোনেন্ট এর নিজস্ব ডাটা।  change the anykind of situation অথবা স্টেট হলো কোন কিছুর অবস্থা পরিবর্তন করা। কোথায় ব্যবহৃত হয় ? 
=> যে কোন ডাটা অথবা ডিজিট বাড়ানো অথবা কমানো জন্য স্টেট ব্যবহৃত হয়। যদি আমরা উদাহরন হিসাবে একটা ওয়েব-এ্যাপ্লিকেশন এর ‍শপিং চার্টকে ধরে নিতে পারি।
=> যদি কোনো ওয়েভ এ্যাপ্লিকেশন এ ডাটা থাকে এবং ওই ডাটা ব্রাউসারে দেখাতে হলে স্টেট ব্যবহার করতে হবে এবং সেই ডাটা চেঞ্জ করতে হবে তখন স্টেট ব্যবহার করতে হয়।
=> স্টেট বা কম্পোনেন্ট মাঝে মধ্যে স্টোর মত কাজ করে । এর 2টা মেইন ফাংশন আছে যেটা সাবস্ক্রাইভ করা যায়। যখন চেঞ্জ হবে তখন প্রত্যেকের কাছে নটিফিকেশন পাঠাবে এই
স্টেট আর ভিউলেয়ার অথবা জেএসএক্স মধ্যে দিয়ে।
=> this.setState মাধ্যেমে যে কোন state পরিববর্তন করা যায়।
=> state পরিববর্তন হওয়ার পরে আবার render() ফাংশনে কল হয়।
=> state জেনারেল জাভাস্ক্রিপ্ট অবজেক্ট। এটাকে inmuted অবস্থায় পরিবর্তন করতে হবে।

 - ডাটা ভ্যারিয়্যবেল মধ্যে না রেখে স্টেট মধ্যে রাখতে হবে।  হোক সেটা অ্যারে অথবা অবজেক্ট।
 - যেখানে ডায়নামিক ডাটা থাকবে, ডাটা পরিবর্তন করতে হবে, ডাটা পরিবতর্ন সাথে ভিউ চেঞ্জ হবে সেখানে state হবে।
 - স্টেট আপডেট করতে হলে setState() ব্যবহার করতে হবে।
 - setState() এর মধ্যে আমরা ফাংশন র্আগুমেন্ট পাঠাতে পারি। উদাহরন হিসাবে আমরা prev.count + 1 নিতে পারি।


উদাহরন অনুযায়ী বেসিক কনসেপ্ট হল:
#-----------------------------------------------------------------------------------
```
function MovieCounter(){
const [count, setCount] = useState(5) 
// keep in mind : count : set, setCount: update
const handleClick  = () => {
    setCount(count + 1)
  }
  return (
    <div>
      <button onClick={handleClick}>Add Movie</button>
      <h3>number of movie : {count}</h3>
    </div>
  )
}
```
#-----------------------------------------------------------------------------------
প্রথম মাধ্যম- কিভাবে কাজ করে !
```
import React, { Component } from 'react'
class App extends Component{
  constructor(props){
    super(props)
    this.count = 5;
    this.state = {
      count: 0
    }
  }
  count = 0;
  render(){
    //console.log(this.count);
    return(
      <div className='App'>
          <h1>Why do we need state</h1>
          <h2>Count = {this.state.count}</h2>

          <button onClick={() => {
            //this.count++;
            this.setState({count: this.state.count + 1})
            console.log('clicked....', this.state.count+1);
          }}>
            increment
          </button>
      </div>
    );
  }
}
export default App;
```
দ্বিতীয় মাধ্যম-
```
state = {
  count: 0;
}
```
আপডেট স্টেট- এইটা একটা রুলস যেটার মাধ্যমে স্টেট আপডেট করতে পারি
```
this.setState({count: this.state.count + 1})
```
কিছু কিছু সময়ে স্টেট এর পরিবর্তন করার প্রয়োজন দরকার হতে পারে সেজন্য আমরা যা করতে পারি তা হলো
```
 <button onClick={() => {
   this.setState(prev => {
       return {
         count: prev.count + 1
       }
   })
 }}>
   increment
 </button>
```
এ্যাসিক্রোনাইজ প্রবলেম এর জন্য আমরা এই ভাবে ডিক্লায়ার করতে পারি।
```
<button onClick={() => {
  this.setState(prev => {
      return {
        count: prev.count + 1
      }
  },
  ()=> {
    console.log('clicked ... ', this.state.count)
  })
}}>
  increment
</button>
```
