<!DOCTYPE html>
<html>
<head>
    <style>
        h1 {
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>To do list</h1>
    
</body>
</html>
 



<!DOCTYPE html>
<html lang="en">
<head>
    <title>Simple To Do List</title>
    <!--Google Font-->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&display=swap" rel="stylesheet">
    <!--Font Awesome CDN-->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div id="newtask">
            <input type="text" placeholder="Task to be done..">
            <button id="push">Add</button>
        </div>
        <div id="tasks"></div>
    </div>
    <!--Script-->
    <script src="script.js"></script>
</body>
</html>

<style>


*,
*:before,
*:after{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
body{
    height: 100vh;
    background: linear-gradient(
        135deg,
        #8052ec,
        #d161ff
    );
}
.container{
    width: 40%;
    min-width: 450px;
    position: absolute;
    margin: auto;
    left: 0;
    right: 0;
    top: 30px;
    padding: 30px 40px;
}
#newtask{
    position: relative;
    background-color: #ffffff;
    padding: 30px 20px;
    border-radius: 5px;
    box-shadow: 0 15px 30px rgba(0,0,0,0.3);
}
#newtask input{
    width: 70%;
    width: 70%;
    height: 45px;
    font-family: 'Poppins',sans-serif;
    font-size: 15px;
    border: 2px solid #d1d3d4;
    padding: 12px;
    color: #111111;
    font-weight: 500;
    position: relative;
    border-radius: 5px;
}
#newtask input:focus{
    outline: none;
    border-color: #8052ec;
}

#newtask button{
    position: relative;
    float: right;
    width: 20%;
    height: 45px;
    border-radius: 5px;
    font-family: 'Poppins',sans-serif;
    font-weight: 500;
    font-size: 16px;
    background-color: #8052ec;
    border: none;
    color: #ffffff;
    cursor: pointer;
    outline: none;
}
#tasks{
    background-color: #ffffff;
    padding: 30px 20px;
    margin-top: 60px;
    border-radius: 10px;
    box-shadow: 0 15px 30px rgba(0,0,0,0.3);
    width: 100%;
    position: relative;
}
.task{
    background-color: #ffffff;
    height: 50px;
    padding: 5px 10px;
    margin-top: 10px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 2px solid #d1d3d4;
    cursor: pointer;
}
.task span{
    font-family: 'Poppins',sans-serif;
    font-size: 15px;
    font-weight: 400;
}
.task button{
    background-color: #8052ec;
    color: #ffffff;
    height: 100%;
    width: 40px;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    outline: none;
}
.completed{
    text-decoration: line-through;
}
</style>


<header>
    <script>
document.querySelector('#push').onclick = function(){
    if(document.querySelector('#newtask input').value.length == 0){
        alert("Please Enter a Task")
    }
    else{
        document.querySelector('#tasks').innerHTML += `
            <div class="task">
                <span id="taskname">
                    ${document.querySelector('#newtask input').value}
                </span>
                <button class="delete">
                    <i class="far fa-trash-alt"></i>
                </button>
            </div>
        `;

        var current_tasks = document.querySelectorAll(".delete");
        for(var i=0; i<current_tasks.length; i++){
            current_tasks[i].onclick = function(){
                this.parentNode.remove();
            }
        }

        var tasks = document.querySelectorAll(".task");
        for(var i=0; i<tasks.length; i++){
            tasks[i].onclick = function(){
                this.classList.toggle('completed');
            }
        }

        document.querySelector("#newtask input").value = "";
    }
}
</script>
</head>
<body>       
