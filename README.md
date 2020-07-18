<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<style>
    .btn {
    display: block;
    margin: 0 auto;
    padding: 10px;
    background-color: #4e4ebb;
    color: #fff;
    border: solid 0px;
    font-size: 20px;
    }
    .modal {
    display: none;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color:#1c7bfceb;
    }
    .modal-body img{
        width: 100%;
    }
    .modal-header h2{
    text-align: center;
    }
    .close {
    font-size: 28px;
    font-weight: bold;
    position: absolute;
    top: 0;
    left: 100%;
    transform: translate(-100%, -18%);
}
    .close, span:hover {
        cursor: pointer;
    }
</style>

<body>
    <button class="btn" id="openModal">Открыть</button>

    <div class="modal" id="modal">
        <div class="modal-header"><h2>Заголовок модалки</h2>
            <span class="close">X</span>
        </div>
        <div class="modal-body">
           <a href="#" title="#"><img src="https://big-seo.ru/wp-content/uploads/2020/02/javscript-1.png" alt="#"></a> 
        </div>
    </div>
    
    <script>
        let btn = document.getElementById('openModal');
        let modal = document.getElementById('modal');
        let xClose = document.querySelector('.close');

        btn.onclick = function () {
          let openModal = modal.style.display = 'block';
          let showClose = xClose.style.display = 'inherit';
        };
        xClose.onclick = function () {
            xClose.style.display = 'none';
            modal.style.display = 'none';
        };
        
        // Хотел сделать чтобы при клике за пределами модалки, тоже закрывалось - не получилось.

        window.onclick = function () {
        if (openModal.style.display === 'block' ) {      
            openModal.style.display = 'none';
          } else if (showClose.style.display === 'inherit') { 
            showClose.style.display = 'none';
          };
         }; 


        // Пользовался уже гуглом - тоже не срабатывает ( 
      /*   window.onclick = function(event) {
            if (event.target == modal) {
            modal.style.display = "none";
             }
        }; */
    </script>
</body>
</html>
