// src/components/StreamList.js
import React, { useState } from 'react';

const StreamList = () => {
  const [input, setInput] = useState('');
  const [items, setItems] = useState([]);

  const handleChange = (e) => {
    setInput(e.target.value);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (input.trim()) {
      setItems([...items, input.trim()]);
      setInput('');
    }
  };

  return (
    <div className="streamlist">
      <h1>StreamList</h1>
      <form onSubmit={handleSubmit}>
        <input
          type="text"
          value={input}
          onChange={handleChange}
          placeholder="Add to your streamlist..."
        />
        <button type="submit">Add</button>
      </form>
      <ul>
        {items.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
};

export default StreamList;
// src/components/Movies.js
import React from 'react';

const Movies = () => {
  return <div className="movies"><h1>Movies Page</h1></div>;
};

export default Movies;
// src/components/Cart.js
import React from 'react';

const Cart = () => {
  return <div className="cart"><h1>Cart Page</h1></div>;
};

export default Cart;
// src/components/About.js
import React from 'react';

const About = () => {
  return <div className="about"><h1>About Page</h1></div>;
};

export default About;
/* src/styles/App.css */
body {
  font-family: 'Roboto', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f0f0f0;
}

.app {
  text-align: center;
}

nav {
  background-color: #333;
  padding: 1rem;
}

nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
}

nav ul li {
  margin: 0 1rem;
}

nav ul li a {
  color: white;
  text-decoration: none;
}

nav ul li a:hover {
  text-decoration: underline;
}

.streamlist,
.movies,
.cart,
.about {
  padding: 2rem;
}

form {
  margin-top: 1rem;
}

input {
  padding: 0.5rem;
  font-size: 1rem;
}

button {
  padding: 0.5rem;
  font-size: 1rem;
  margin-left: 0.5rem;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 1rem;
}

li {
  background-color: #fff;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  border-radius: 4px;
}
