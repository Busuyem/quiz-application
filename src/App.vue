<template>
  <div class="container">
      <header>
        <h1>Quizes</h1>
        <input type="text" placeholder="Search...">
      </header>

      <div class="container-options">
        <div class="card">
          <img src="https://th.bing.com/th/id/OIP.XW5L06-psFC_oVws6Kgq2QHaFS?pid=ImgDet&rs=1" alt="">
          <div class="card-text">
            <h2>Maths</h2>
            <p>15 questions</p>
          </div>
        </div>
      </div>
  </div>
</template>

<style>
    .container{
      max-width: 1000px;
      margin: 0 auto;
      margin-bottom: 10px;
      margin-top: 30px;
    }

    header{
      display: flex;
      align-items: center;
    }

    header h1{
      font-weight: bold;
      margin-right: 30px;
    }

    header input{
      border-radius: 5px;
      border: 0px;
      background-color: rgba(130, 120, 110, 0.1);
      padding:10px;
    }

    .container-options{
      display: flex;
      flex-wrap: wrap;
      padding: 10px;
    }

    .card{
      width: 310px;
      overflow: hidden;
      border-radius: 2px;
      box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
      margin-bottom: 35px;
      margin-right: 20px;
      margin-top: 30px;
      cursor: pointer;
    }
    

    .card img{
      width: 100%;
      height: 150px;
      margin: 0;
    }

    .card .card-text{
      padding: 15px;

    }

    .card h2{
      font-weight: bold;
    }
</style>