# WHEELDEAL
To deal with local area car showroom .
wheel-deal/
├── backend/
│   ├── app.js
│   ├── models/
│   ├── routes/
│   └── config/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.js
│   │   └── index.js
├── .gitignore
├── package.json
├── README.md
const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
const app = express();

// Middleware
app.use(cors());
app.use(express.json());

// Database connection
mongoose.connect('mongodb://localhost:27017/wheel-deal', {
  useNewUrlParser: true,
  useUnifiedTopology: true,
});

// Routes
app.get('/', (req, res) => {
  res.send('API is running...');
});

// Listen on port
const PORT = process.env.PORT || 5000;
app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
