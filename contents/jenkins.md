# Jenkins

## Getting and Setting the next build number

You can access the build number through the Jenkins script console (Manage Jenkins -> Script Console)

To find out the next build number:
```Jenkins.instance.getItemByFullName("YourJobName").getNextBuildNumber()
```

Setting the next build number:
```Jenkins.instance.getItemByFullName("YourJobName").updateNextBuildNumber(42)
```
