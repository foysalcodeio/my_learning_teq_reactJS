Axios

```
import axios from 'axios';

const uploadFile = (file) => {
  // Create a FormData object
  const formData = new FormData();

  // Append the file to the FormData object
  formData.append('file', file);

  // You can also append other data if needed
  // formData.append('key1', 'value1');
  // formData.append('key2', 'value2');

  // Set headers for the request
  const config = {
    headers: {
      'Content-Type': 'multipart/form-data',
    },
  };

  // Make the POST request using Axios
  axios.post('your-api-endpoint', formData, config)
    .then(response => {
      console.log(response.data);
    })
    .catch(error => {
      console.error('Error uploading file:', error);
    });
};

// Example usage
const fileInput = document.getElementById('file-input');

fileInput.addEventListener('change', (event) => {
  const file = event.target.files[0];
  uploadFile(file);
});
```
```
