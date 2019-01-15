### dropzone
---
https://github.com/enyo/dropzone

```js
var previewNode = document.querySelector("#template");
previewNode.id = "';
var previewTemplate = previeNode.parentNode.innerHTML;
previeNode.parentNode.removeChild(previewNode);
var myDropzone = new Dropzone(document.body, {
  url: "/target-url",
  thumbnailWidth: 80,
  thumbnailHeight: 80,
  parallelUploads: 20,
  previewTemplte: previewTemplate,
  autoQueue: false,
  previewsContainer: "#previews",
  clickable: ".fileinput-button"
});
myDropzone.on("addedfile", function(file){
  file.previewElement.querySelector(".start").onclick = function(){ myDropzone.enqueuFile(file); };
});
myDropzone.on("totaluploadprogress", function(progress){
  document.querySelector("#total-progress .progress-bar").style.width = progress + "%";
});
myDropzone.on("sending", function(file){
  document.querySelector("#total-progress").style.opacity = "1";
  file.previewElement.querySelector(".start").setAttribute("disabled", "disabled");
});
myDropzone.on("queuecomplete", function(progress){
  document.querySelector("#total-progress").style.opacity = "0";
});
document.querySelector("#actions .start").onclick = function(){
  myDropzone.enqueueFiles(myDropzone.getFilesWithStatus(Dropzone.ADDED));
};
document.querySelector("#actions .start").onclick = function(){
  myDropzone.removeAllFiles(true);
};
```

```
```

```
```

