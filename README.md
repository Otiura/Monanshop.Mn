const express = require('express');
const axios = require('axios');
const { Configuration, OpenAIApi } = require('openai');

const app = express();
app.use(express.json();

const configuration = new Configuration({
  apiKey: process.env.OPENAI_API_KEY
});
const openai = new OpenAIApi(configuration);

app.post('/webhook', async (req, res) => {
  const userMessage = req.body.message;

  const response = await openai.createChatCompletion({
    model: 'gpt-4',
    messages: [{ role: 'user', content: userMessage }]
  });

  const aiReply = response.data.choices[0].message.content;

  // Optionally: logic or memory operations here...

  // Send to ManyChat or other endpoint
  await axios.post('https://api.manychat.com/v2/send', {
    message: aiReply
  }, {
    headers: {
      Authorization: `Bearer ${process.env.MANYCHAT_TOKEN}`
    }
  });

  res.send({ reply: aiReply });
});

module.exports = app;

