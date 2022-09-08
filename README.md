# Assignment2-Paruchuri

# Siva Ram Sai Paruchuri
##### Salar Jung Museum

It is one of the notable National Museums of India.The Salar Jung museum is one of the three national museums of India. <br>Inside Salar Jung Museum are artefacts from the private collections of three generations of Hyderabad’s Salar Jung noble family, and which were acquired between 1829 and 1949.<br>One of them was the **Veiled Rebecca**, an exquisitely carved marble statue of a veiled woman and one of the most popular things to see in the Salar Jung Museum. Another was the collection of **superb Arabic and Persian manuscripts, some even embellished in gold**.

---

## MY HEADING
RG airport
1. go straight
2. take NH-32
3. you will come near cross junction.ahead museum is loacted.

## heading2
near by places are
* fort
* film city
* lumbini park

**[my link](https://github.com/SRS-P/Assignment2-Paruchuri/blob/main/AboutMe.md)**


## Tables

recommended cities

| city | loc  | time travel |
| :--- |  --- | ---         |
|delhi | india gate| 2hrs flight|
|mumbai | taj| 3hrs flight|
|kolkata | temple| 3.5hrs flight|
|vizag | beach| 1hrs flight|



---
### Quotes
> life is like riding a bicycle, to keep balance keep moving *einstein*
> Always remember you are unique *margaret head*

---
## code fencing

> getting html value and use it in controller laravel php

[my link2](https://stackoverflow.com/questions/73643755/getting-html-value-and-use-it-in-controller-laravel-php)

```
<!doctype html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Directory Contents</title>
  <link rel="stylesheet" href=".style.css">
  <script src=".sorttable.js"></script>
</head>

<body>

  <div id="container">
  
    <h1>Directory Contents</h1>
    
    <table class="sortable">
      <thead>
        <tr>
          <th>Filename</th>
          <th>Type</th>
          <th>Size <small>(bytes)</small></th>
          <th>Date Modified</th>
        </tr>
      </thead>
      <tbody>
      <?php
        // Opens directory
        $myDirectory=opendir(".");
        
        // Gets each entry
        while($entryName=readdir($myDirectory)) {
          $dirArray[]=$entryName;
        }
        
        // Finds extensions of files
        function findexts ($filename) {
          $filename=strtolower($filename);
          $exts=split("[/\\.]", $filename);
          $n=count($exts)-1;
          $exts=$exts[$n];
          return $exts;
        }
        
        // Closes directory
        closedir($myDirectory);
        
        // Counts elements in array
        $indexCount=count($dirArray);
        
        // Sorts files
        sort($dirArray);
        
        // Loops through the array of files
        for($index=0; $index < $indexCount; $index++) {
        
          // Allows ./?hidden to show hidden files
          if($_SERVER['QUERY_STRING']=="hidden")
          {$hide="";
          $ahref="./";
          $atext="Hide";}
          else
          {$hide=".";
          $ahref="./?hidden";
          $atext="Show";}
          if(substr("$dirArray[$index]", 0, 1) != $hide) {
          
          // Gets File Names
          $name=$dirArray[$index];
          $namehref=$dirArray[$index];
          
          // Gets Extensions 
          $extn=findexts($dirArray[$index]); 
          
          // Gets file size 
          $size=number_format(filesize($dirArray[$index]));
          
          // Gets Date Modified Data
          $modtime=date("M j Y g:i A", filemtime($dirArray[$index]));
          $timekey=date("YmdHis", filemtime($dirArray[$index]));
          
          // Prettifies File Types, add more to suit your needs.
          switch ($extn){
            case "png": $extn="PNG Image"; break;
            case "jpg": $extn="JPEG Image"; break;
            case "svg": $extn="SVG Image"; break;
            case "gif": $extn="GIF Image"; break;
            case "ico": $extn="Windows Icon"; break;
            
            case "txt": $extn="Text File"; break;
            case "log": $extn="Log File"; break;
            case "htm": $extn="HTML File"; break;
            case "php": $extn="PHP Script"; break;
            case "js": $extn="Javascript"; break;
            case "css": $extn="Stylesheet"; break;
            case "pdf": $extn="PDF Document"; break;
            
            case "zip": $extn="ZIP Archive"; break;
            case "bak": $extn="Backup File"; break;
            
            default: $extn=strtoupper($extn)." File"; break;
          }
          
          // Separates directories
          if(is_dir($dirArray[$index])) {
            $extn="&lt;Directory&gt;"; 
            $size="&lt;Directory&gt;"; 
            $class="dir";
          } else {
            $class="file";
          }
          
          // Cleans up . and .. directories 
          if($name=="."){$name=". (Current Directory)"; $extn="&lt;System Dir&gt;";}
          if($name==".."){$name=".. (Parent Directory)"; $extn="&lt;System Dir&gt;";}
          
          // Print 'em
          print("
          <tr class='$class'>
            <td><a href='./$namehref'>$name</a></td>
            <td><a href='./$namehref'>$extn</a></td>
            <td><a href='./$namehref'>$size</a></td>
            <td sorttable_customkey='$timekey'><a href='./$namehref'>$modtime</a></td>
          </tr>");
          }
        }
      ?>
      </tbody>
    </table>
  
    <h2><?php print("<a href='$ahref'>$atext hidden files</a>"); ?></h2>
    
  </div>
  
</body>

</html>
```
[my link3](https://css-tricks.com/snippets/php/display-styled-directory-contents/)