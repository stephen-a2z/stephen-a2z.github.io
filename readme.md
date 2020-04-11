### Requirements  
- Node.js (Should be at least Node.js 8.10, recommends 10.0 or higher)  
- Git  
### Install node.js  
```bash
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```
### Install hexo
```bash
npm install -g hexo-cli
npm install
```
### write page

```bash
hexo new [layout] title  
```
default layout: `post`, `page` and `draft`
### Drafts
You can use the publish command to move drafts to the source/_posts folder.
```bash
hexo publish [layout] title
```
Block Quote   
Code Block
...  
[tag plug](https://hexo.io/docs/tag-plugins)




