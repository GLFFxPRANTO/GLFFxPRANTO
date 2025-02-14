const express = require('express');
const app = express();

// Render-এর জন্য ডাইনামিক পোর্ট ব্যবহার করুন
const port = process.env.PORT || 3000;

app.get('/', (req, res) => {
    res.send('Server is running!');
});

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

// সার্ভার চালু করুন
app.listen(port, () => {
    console.log(`Server is running on port ${port}`);
});
