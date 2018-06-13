# Kitchen cheatsheet

Kitchen provides a test harness to execute infrastructure code on one or more platforms in isolation.

Start one or more instances
```
kitchen create
````

Use a provisioner to configure one or more instances
```
kitchen converge
```

Prepare to run automated tests. Install busser and related gems on one or more instances
```
kitchen setup
```

Run automated tests on one or more instances
```
kitchen verify
```

Delete all information for one or more instances
```
kitchen destroy
```
