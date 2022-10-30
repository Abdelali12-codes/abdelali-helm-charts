# helm tutorial


# install the helm version (3.7) stable 


# steps to create helm charts

1. create github repo 
2. create empty git local repo
```
git init .
```

3. add remote repo
```
git remote add origin url-of-github-project
```
4. create directory to put all your charts (it is optional, but just to keep your repo tree clean)
```
mkdir helm-charts-source && cd helm-charts-source 
```
5. create your first chart 
```
helm create helm-charts-source/spring-boot-app 
```
6. modify the values.yaml file and the template folder with the manifest your want your chart to have
7. package your helm chart 
```
helm package helm-charts-source/spring-boot-app 
```
8. create the index.yaml file that is mandatory by helm 
```
helm repo index --url url-of-your-github (must be like this: username-of-your-github.github.io/helm-repo-name) .
```
9. add the changes to your local repo
```
git add .
```
10. commit the changes 
```
git commit -am "update repo"
```
11. if you want to add new charts to your helm repo, then follow the same steps starting from step 5
12. to add new chart to the index.yaml file 
```
helm repo index --url (username-of-your-github.github.io/helm-repo-name) --merge index.yaml .
```


