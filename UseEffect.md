# UseEffect
রিয়েক্টে ডায়নামিক ডাটা লোড করা :
এটা অনেকটা সাইড ইফেক্ট এর মত। মাঝে মধ্যে কাজ করার সময় এক্সটারনার কিছু ডিপেন্ডেন্সি উপর নির্ভর করতে হয়। যেমন সার্ভরের ডাটা। এটা জাভাস্ক্রিপ্টের ডিপেন্ট না থেকে র্সাভার মধ্যে ডিপেন্ট থাকে।
বেসিক সার্ভার লোডিং টেস্ট

- এক কথায় সার্ভার লোডির্
```
function Users(){
  const [users, setUsers] = useState([]);
  useEffect(()=>{
    console.log('callilng Effect')
  })
  return (
    <div>
      <h3>Dynamic Users</h3>
    </div>
  )
}
```
fetch লোডিং টেস্ট
```
function Users(){
  const [users, setUsers] = useState([]);
  useEffect(()=>{
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(res => res.json())
    .then(data => setUsers(data)) // or you can test - .then(data => console.log(data))
  })
  console.log(users)
```
অনেক সময় এমন হয় যে কনসোলে ডাটা বার বার বার রিপিট করে তার জন্য জাস্ট , []} ব্যবহার করতে হবে।
```
  useEffect(()=>{
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(res => res.json())
    .then(data => setUsers(data))
  }, [])
```
সার্ভার থেকে ডাটা লোড করার সবথেকে সুন্দর উদাহরন
```
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <Users></Users>
      </header>
    </div>
  );
}

function Users(){
  const [users, setUsers] = useState([]);

  useEffect(()=>{
    fetch('https://jsonplaceholder.typicode.com/todos')
    .then(res => res.json())
    .then(data => setUsers(data))
  }, [])

  return (
    <div>
      <h3>Dynamic Users : {users.length}</h3>
      <ul>
      {
        console.log(users)
      }
      {
        //console.log(users)
        users.map(user => <h4>{user.title}</h4>)
      }
      </ul>
    </div>
  )
}
```

