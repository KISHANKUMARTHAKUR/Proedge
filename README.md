# Proedge

Design and build the following:

1. A frontend that accepts a comma-separated list of roll numbers (front end must be in React or Nextjs)

2. On entering the value and pressing submit, a request should be sent to the backend (write a backend API in node js to accept this from the frontend)

3. From the backend, you have to call an external API to get the pass/fail result, as follows:
http://proedge.me/test.php?rollnumber=123

In the above, the roll number is the value to be passed, and it will return pass or fail results. This external API only accepts 1 roll number per call.

4. From the backend, when all the roll number results are known, return the results to the frontend

5. On the frontend, display the roll numbers and their result in a tabular format

6. Run the above for this input: 5,6,9,12,18,20,25,30,32,36,37,38,40,42,45,47,49,50

Expected solution:

1. The source code of the frontend and backend to be uploaded to GitHub along with a readme file.

2. Readme must
- explain components of the code
- mention all libraries and plugins used
- list all test cases run along with test data and screenshots

3. Extra points for hosting this solution on Heroku or AWS (free tier) or somewhere online
-----------------------------


{
  "name": "firstproject",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies":  {
    "next": "^9.1.2",
    "react": "^16.11.0",
    "react-dom": "^16.11.0"
  }
}


 = {
      items: [],
      isLoaded: false,
    };
  }

  componentDidMount() {
    fetch('http://proedge.me/test.php?rollnumber=123')
      .then(res => res.json())
      .then(result => {
        this.setState({
          isLoaded: true,
          items: result
        });
      });
  }

  render() {
    const { items } = this.state;
    if (!isLoaded) {
      return <div>Loading ... </div>;
    } else {
      return (
        <ul>
          {items.map(item => (
            <li key={item.id}>
              <h3>{item.title}</h3>
              <p>{item.body}</p>
            </li>
          ))}
        </ul>
      );
    }
  }
}
Fetching Data - Ha
