## Standard Service Layout

[Back to index](README.md)

---
### Linux
```bash
sudo mkdir -p /srv/{apps,data,models,ingress,observability}
sudo chown -R $USER:$USER /srv
```

### MacOS
This is due to MacOS not giving users direct access to / without aditional modifications since MacOS is a headed system (eventhough it might be used as a server)
So unlike Linux **/srv** directory, we will put it under **/home/USERNAME/srv** directory

```bash
sudo mkdir -p ~/srv/{apps,data,models,ingress,observability}
sudo chown -R $USER:$USER ~/srv
```
---