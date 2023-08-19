# todoapp

<!DOCTYPE html>
<!-- saved from url=(0036)https://todoappbyaditya.netlify.app/ -->
<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>
        To Do List
    </title>
    <style>
        body {
            background-color:azure;
        }
        div 
        {
            border:2px solid black;
        }
        #main 
        {
            display:inline-block;
            height:700px;
            width:500px;
            background-image: url('ab.jpg');
            background-size:700px 500px ;
        }
        #temp 
        {
            margin-left:700px;
            margin-top: -600px;
            height:335px;
            width:316px;
        }
        input 
        {
            width:307px;
        }
        .subox
        {
            color:aliceblue;
            border:0px solid black;
            font-size:25px;
            padding: 5px;
            height:50px;
        }
        .eye,.trash
        {
            float:right;
         
            height:45px;
        }
        .plus 
        {
            margin-left:200px;
            height: 45px;
        }
        .description
        {
            display:none;
        }
        .ignore 
        {
            display:none;
        }
    
    </style>
</head>
<body>
    <div class="box" id="main">
<!--
        <div class="subox" id="box1">
            Complete the Science Project 
            <img class ='trash' id="trash1" onclick="trash(this.id);" src="trash.png">
            <img class ='eye' id="eye1" onclick="add(this.id);" src="eye.png">
            <input type="text" class="description">
        </div>

-->

        <div class="subox" id="addbox">

            <img class="plus" onclick="add();" src="./To Do List_files/plus.png">

        </div>

        
    </div>

    <div class="box" id="temp">

        <input type="text" class="text" id="desctext">
        <script>
            let a = document.getElementById('desctext');
            a.value="Enter the task's title here";
        </script>
        
        <textarea id="w3review" name="w3review" rows="20" cols="40">Enter the description of the task here, then click on the plus button on the left most screen
        </textarea>
    
    </div>


<script>

let count = 0;//Number of Tasks

let lastid=0;

function test(id)
{
    console.log(id);
}

function add(id)
{
    //when add is clicked
    //clear tesxt area and input 

    const el = document.createElement('div');
    el.setAttribute('class', 'subox');
    let elemid = "box"+count;
    el.setAttribute('id', elemid);
    el.textContent = '';

    //const box = document.getElementById('box');

    // Insert before existing child:
    const list = document.getElementById("addbox");
    list.insertBefore(el, list.children[0]);


    let b = document.getElementById(elemid);

    let htmlcontent1,htmlcontent2,htmlcontent3;

    // adding input things in new task

    let c = document.getElementById("desctext");
    let d = document.getElementById("w3review");

    c = c.value;
    d = d.value;

    htmlcontent1 = c + "<img class='trash' id='trash" + count+"'"+" onclick='trash(this.id);' src='trash.png'>";
    htmlcontent2 = "<img class='eye' id='eye" + count+"'"+" onclick='eye(this.id);' src='eye.png'>";
    htmlcontent3 = "<span class='description' id='desc"+count+"'>"+d+"</span>";
    //<img class ='trash' id="trash1" onclick="trash(this.id);" src="trash.png">
      //      <img class ='eye' id="eye1" onclick="add(this.id);" src="eye.png">
        //    <input type="text" class="description">
    
    b.innerHTML = htmlcontent1+htmlcontent2+htmlcontent3;
    count++;

    console.log(id);
}

function trash(id)
{
    //remove trash keyword and replace it with box
    let elementtoberemoved;
    let letter = id.charAt(id.length-1);
    let elementsid = "box"+letter;
    elementtoberemoved = document.getElementById(elementsid);
    elementtoberemoved.remove();
    console.log(id);
}

function eye(id)
{
    //remove trash keyword and replace it with box
    let elementtoberemoved;
    let letter = id.charAt(id.length-1);
    let elementsid = "desc"+letter;

    elementtobeshown = document.getElementById(elementsid);

    descarea = document.getElementById("w3review");

    descarea.value = elementtobeshown.innerText;


    let a = document.getElementById("desctext");
    let b = "box"+letter;
    let c = document.getElementById(b);
    c = c.innerText;
    a.value = c;
    console.log(id);
}

</script>


</body></html>
