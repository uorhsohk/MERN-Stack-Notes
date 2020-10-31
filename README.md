# MERN-Stack-Notes

## POST-Request Does NOT Work

so if you have made a POST-Request using express, e.g.:

```
app.post('/api/notes', (req, res) => {
  const note = req.body;
  res.json(note);
});
```

and you get nothing back (Content-Length: 0), then most likely you have forgotten to import the following:

```
app.use(express.json())
```

Reason:

The express json is a middleware, and middlewares are functions that can be used for handling request and response objects.
The json parse takes take from the request and parses it into a JS  Object and assign it then to the *new* body property.
