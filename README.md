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
