# my_learning_teq_reactJS
#  কম্পোনেন্ট এবং প্রপস

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
