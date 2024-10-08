# Design Guidelines
![Image](/Images/design.jpg)  
Toxiq must stick to the same design regardless of platform so all users would have the same experiance regardless of the platform 

### Figma 
[Figma Design Files](https://www.figma.com/design/bHUKMe5lCrLMKzhCckjvPC/Toxiq-App?node-id=24-853&t=3LEsKjmq0bSqOVw0-0)

### Fonts
[Roboto](https://fonts.google.com/specimen/Roboto)  

### Social Preview
refer to the following [docs](https://github.com/FishieDotCom/Toxiq-Assets?tab=readme-ov-file#social-preview) for infomation regarding social preview

### Icons
Using the same Icons across Toxiq apps is a must as users expect the same icons to do the same task across platforms and apps  

Icon Resources  
- [Segoe Fluent Icons](https://learn.microsoft.com/en-us/windows/apps/design/style/segoe-fluent-icons-font)  
- [Icon Catalog](https://master--628d031b55e942004ac95df1.chromatic.com/?path=/docs/icons-catalog--page)

<details>
<summary><b>Icons</b> <i>(click to expand)</i></summary>  

#### Comment Icon
 <svg width="50" height="50" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M5.25 18A3.25 3.25 0 0 1 2 14.75v-8.5A3.25 3.25 0 0 1 5.25 3h13.5A3.25 3.25 0 0 1 22 6.25v8.5A3.25 3.25 0 0 1 18.75 18h-5.738L8 21.75a1.25 1.25 0 0 1-1.999-1V18h-.75Zm7.264-1.5h6.236a1.75 1.75 0 0 0 1.75-1.75v-8.5a1.75 1.75 0 0 0-1.75-1.75H5.25A1.75 1.75 0 0 0 3.5 6.25v8.5c0 .966.784 1.75 1.75 1.75h2.249v3.75l5.015-3.75Z" fill="#DDE6E8"/></svg>     

Icon Name 
```CommentRegular```  
Unicode ```e90a```


#### Voting
<svg width="50" height="50" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M16.5 17.985c0 2.442-1.14 4.198-3.007 4.198-.975 0-1.341-.542-1.69-1.795l-.207-.772c-.101-.359-.277-.97-.527-1.831a.249.249 0 0 0-.03-.065l-2.866-4.486a5.886 5.886 0 0 0-2.855-2.327l-.473-.18A2.75 2.75 0 0 1 3.13 7.634l.404-2.087A3.25 3.25 0 0 1 5.95 3.011l7.628-1.87a4.75 4.75 0 0 1 5.733 3.44l1.415 5.55a3.25 3.25 0 0 1-3.15 4.052h-1.822c.496 1.633.746 2.893.746 3.802ZM4.6 7.92a1.25 1.25 0 0 0 .78 1.405l.474.182a7.385 7.385 0 0 1 3.582 2.92l2.867 4.485c.09.14.159.294.205.454l.552 1.92.212.792c.14.488.21.605.22.605.868 0 1.507-.984 1.507-2.698 0-.885-.326-2.336-.984-4.315a.75.75 0 0 1 .711-.987h2.85a1.751 1.751 0 0 0 1.696-2.182l-1.415-5.55a3.25 3.25 0 0 0-3.923-2.353l-7.628 1.87a1.75 1.75 0 0 0-1.301 1.366L4.6 7.92Z" fill="#DDE6E8"/></svg>  <svg width="50" height="50" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M16.5 5.202c0-2.442-1.14-4.199-3.007-4.199-1.026 0-1.378.602-1.746 2-.075.289-.112.43-.151.568-.101.359-.277.97-.527 1.831a.25.25 0 0 1-.03.065L8.174 9.953a5.885 5.885 0 0 1-2.855 2.326l-.473.181a2.75 2.75 0 0 0-1.716 3.092l.404 2.086a3.25 3.25 0 0 0 2.417 2.538l7.628 1.87a4.75 4.75 0 0 0 5.733-3.44l1.415-5.55a3.25 3.25 0 0 0-3.15-4.052h-1.822c.496-1.633.746-2.893.746-3.802ZM4.6 15.267a1.25 1.25 0 0 1 .78-1.406l.474-.18a7.385 7.385 0 0 0 3.582-2.92l2.867-4.486c.09-.141.159-.294.205-.455.252-.865.428-1.479.53-1.843.044-.153.085-.308.159-.592.19-.722.283-.882.295-.882.868 0 1.507.984 1.507 2.7 0 .884-.326 2.335-.984 4.314a.75.75 0 0 0 .711.987h2.85a1.751 1.751 0 0 1 1.696 2.182l-1.415 5.55a3.25 3.25 0 0 1-3.923 2.353l-7.628-1.87a1.75 1.75 0 0 1-1.301-1.366L4.6 15.267Z" fill="#DDE6E8"/></svg>

Icon Name 
```ThumbDislikeRegular```  
Unicode ```e8e0```  

Icon Name 
```ThumbLikeRegular```  
Unicode ```e8e1```

##### Voted   
when a user votes the icon must be filled to indicate that the users action has been recorded


<svg width="50" height="50" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M15.057 9.004c.46-1.427.693-2.676.693-3.753 0-2.399-.939-4.248-2.5-4.248-.847 0-1.109.505-1.437 1.747.017-.065-.163.634-.215.821-.101.36-.277.97-.527 1.831a.247.247 0 0 1-.03.065L8.175 9.953A5.885 5.885 0 0 1 5.32 12.28l-1.257.481a1.75 1.75 0 0 0-1.092 1.968l.686 3.538a2.25 2.25 0 0 0 1.673 1.757l8.25 2.022a4.75 4.75 0 0 0 5.733-3.44l1.574-6.173a2.75 2.75 0 0 0-2.665-3.429h-3.165Z" fill="#DDE6E8"/></svg><svg width="50" height="50" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M15.057 14.183c.46 1.427.693 2.676.693 3.753 0 2.399-.939 4.248-2.5 4.248-.8 0-1.078-.45-1.383-1.547l-.27-1.021c-.1-.359-.276-.97-.526-1.831a.246.246 0 0 0-.03-.065l-2.866-4.486a5.886 5.886 0 0 0-2.855-2.327l-1.257-.48A1.75 1.75 0 0 1 2.97 8.458l.686-3.539A2.25 2.25 0 0 1 5.33 3.163l8.25-2.022a4.75 4.75 0 0 1 5.733 3.44l1.574 6.173a2.75 2.75 0 0 1-2.665 3.429h-3.165Z" fill="#DDE6E8"/></svg>

#### Echo
Echo is Toxiq's version of a sharing   

<svg width="50" height="50" fill="none" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M6.747 4h3.464a.75.75 0 0 1 .102 1.493l-.102.007H6.747a2.25 2.25 0 0 0-2.245 2.096l-.005.154v9.5a2.25 2.25 0 0 0 2.096 2.245l.154.005h9.5a2.25 2.25 0 0 0 2.245-2.096l.005-.154v-.498a.75.75 0 0 1 1.494-.101l.006.101v.498a3.75 3.75 0 0 1-3.55 3.745l-.2.005h-9.5a3.75 3.75 0 0 1-3.745-3.55l-.005-.2v-9.5a3.75 3.75 0 0 1 3.55-3.745l.2-.005h3.464-3.464ZM14.5 6.52V3.75a.75.75 0 0 1 1.187-.61l.082.069 5.994 5.75c.28.268.306.7.077.997l-.077.085-5.994 5.752a.75.75 0 0 1-1.262-.434l-.007-.107v-2.725l-.344.03c-2.4.25-4.7 1.33-6.914 3.26-.52.453-1.323.025-1.237-.658.664-5.32 3.446-8.252 8.195-8.62l.3-.02V3.75v2.77ZM16 5.509V7.25a.75.75 0 0 1-.75.75c-3.874 0-6.274 1.676-7.312 5.157l-.079.279.352-.237C10.45 11.737 12.798 11 15.251 11a.75.75 0 0 1 .743.648l.007.102v1.743L20.16 9.5l-4.16-3.991Z" fill="#DDE6E8"/></svg>

Icon Name 
```ShareRegular```  
Unicode ```e72d```

</details>
