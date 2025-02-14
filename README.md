const express = require('express');
const app = express();
const port = process.env.PORT || 3000;

// Route to handle the request
app.get('/pranto/', (req, res) => {
    const uid = req.query.uid;
    const region = req.query.region;

    if (!uid || !region) {
        return res.status(400).json({ error: 'Missing parameters' });
    }

    // Example logic - Replace with actual data
    const visits = 22;

    const responseText = `PLAYER GOT ${visits} VISIT..CONTACT @ASIBHASANPRANTOO`;
    return res.json({ message: responseText });
});

// Start the server
app.listen(port, () => {
    console.log(`Server running on port ${port}`);
});
