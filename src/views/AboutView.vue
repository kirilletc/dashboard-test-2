<template>
  <div class="about">
    <div class="test-container">
    <div class="header">
        <div class="logo"></div>
        <div class="header__right">
            <button class="help-button">Help</button>
            <button class="upgrade-button">UPGRADE</button>
            <div class="userpic"></div>
        </div>
    </div>

    <div class="subheader">
        <div class="tabs-container">
            <div class="tab tab-active">Analyze</div>
            <div class="tab">My campaigns</div>
            <div class="tab">Configure</div>
        </div>
    </div>

    <div class="dashboard-container">
        <div class="dashboard-container__controls">
            <button class="create-button">Create new</button>
            <div class="dashboard-container__controls__row" @click="displayEven">
                <div class="icon1"></div>
                <div class="dashboard-container__controls__row__right">
                    <div class="controls-title">Display rows 2,4,6 etc</div>
                   
                    <div class="controls-subtitle">Display rows 2,4,6 etc</div>
                </div>
            </div>
            <div class="dashboard-container__controls__row" @click="displayOdd">
                <div class="icon2"></div>
                <div class="dashboard-container__controls__row__right">
                    <div class="controls-title">Display rows 1,3,5 etc</div>
                    <div class="controls-subtitle">Display rows 1,3,5 etc</div>
                </div>
            </div>
            <div class="dashboard-container__controls__row" @click="displayAll">
                <div class="icon3"></div>
                <div class="dashboard-container__controls__row__right">
                    <div class="controls-title">Display all</div>
                    <div class="controls-subtitle">Display all</div>
                </div>
            </div>
        </div>
        <div class="dashboard-container__table">
            <div class="dashboard-container__table__row">
                <div class="table-header">Dashboard</div>
                <div class="table-right">
                    <div class="table-date">Aug 21, 2021 ?? Sep 21 2021</div>
                    <div class="table-print"></div>
                    <div class="table-download"></div>
                </div>
            </div>
            <div class="table-dashboard">
                <div class="table-dashboard__row">
                    <div class="table-dashboard__row__col">Data</div>
                    <div class="table-dashboard__row__col">Summary1</div>
                    <div class="table-dashboard__row__col">Summary2</div>
                    <div class="table-dashboard__row__col">Summary3</div>
                    <div class="table-dashboard__row__col">Summary4</div>
                    <div class="table-dashboard__row__col">Summary5</div>
                </div>
            </div>
            <div class="item angled-bg" id="charItem" data-searchable>
            <div class="table-dashboard-1">
                <div class="table-dashboard__row standart-row">
                    <div class="table-dashboard__row__col">1</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">92</div>
                    <div class="table-dashboard__row__col">8</div>
                    <div class="table-dashboard__row__col">1</div>
                </div>
                <div class="table-dashboard__row">
                    <div class="table-dashboard__row__col">2</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">92</div>
                    <div class="table-dashboard__row__col">8</div>
                    <div class="table-dashboard__row__col">1</div>
                </div>
                <div class="table-dashboard__row">
                    <div class="table-dashboard__row__col">3</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">92</div>
                    <div class="table-dashboard__row__col">8</div>
                    <div class="table-dashboard__row__col">1</div>
                </div>
                <div class="table-dashboard__row">
                    <div class="table-dashboard__row__col">4</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">186</div>
                    <div class="table-dashboard__row__col">92</div>
                    <div class="table-dashboard__row__col">8</div>
                    <div class="table-dashboard__row__col">1</div>
                </div>
            </div>
            </div>
            <div class="table-dashboard">
                <div class="table-dashboard__row">
                    <div class="table-dashboard__row__col"><input type=search data-search id="search" autocomplete="off"></div>
                    <div class="table-dashboard__row__col"><div class="search1"></div></div>
                    <div class="table-dashboard__row__col"><div class="search2"></div></div>
                    <div class="table-dashboard__row__col"><div class="search3"></div></div>
                    <div class="table-dashboard__row__col"><div class="search4"></div></div>
                    <div class="table-dashboard__row__col"><div class="search5"></div></div>
                </div>
            </div>
        </div>
    </div>
    
</div>
</div>
</template>
<script>
    export default {
        mounted() {
        document.querySelector('[data-search]').addEventListener('keyup',filter)
        function filter(){
          var term = document.querySelector('[data-search]').value
          var tag = document.querySelectorAll('[data-searchable] .table-dashboard-1 .table-dashboard__row')
          let i = 0;
          for (i=0;i<tag.length;i++){
            if (tag[i].querySelector('.table-dashboard__row__col:nth-child(1)').innerHTML.indexOf(term) !== -1){
              tag[i].style.display = 'flex'
            } else {
              tag[i].style.display = 'none'
            }
          }
        }
    },
      methods: {
        displayEven() {
          document.querySelectorAll(".table-dashboard-1 .table-dashboard__row:nth-child(odd)").forEach((e) => {e.style.display = "none"});
        },
        displayOdd() {
          document.querySelectorAll(".table-dashboard-1 .table-dashboard__row:nth-child(even)").forEach((j) => {j.style.display = "none"});
        },
        displayAll() {
          document.querySelectorAll(".table-dashboard-1 .table-dashboard__row").forEach((k) => {k.style.display = "flex"});
        }
      }
    };
</script>
<style lang="css">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap');

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    box-sizing: border-box;

}

.test-container {
    width: 1440px;
    height: 574px;
    ackground: #E2F0F0;
    box-shadow: 0px 33px 43px rgba(0, 0, 0, 0.1), 0px 9.94853px 12.9632px rgba(0, 0, 0, 0.0651589), 0px 4.13211px 5.38427px rgba(0, 0, 0, 0.05), 0px 1.4945px 1.94738px rgba(0, 0, 0, 0.0348411);
    border-radius: 20px;
    background: #E2F0F0;
}

.header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 64px;
    background: #FFF;
/*    border-bottom: 1px solid gray;*/
    padding: 0 16px;
}

.logo {
    background: url('../assets/icons/logo.png');
    width: 179px;
    height: 55px;
    background-repeat: no-repeat;
}

.header__right {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    gap: 16px;
}

.help-button {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    min-width: 96px;
    height: 40px;
    padding: 8px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0.44px;
    color: #5E6366;
    border-radius: 10px;
    background: url('../assets/icons/help-circle.png'), #F7F9FA;
    background-repeat: no-repeat;
    background-position: 93% center;
    border: none;

}

.upgrade-button {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    min-width: 96px;
    height: 40px;
    padding: 8px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 16px;
    letter-spacing: 0.75px;
    color: #367BF5;
    border-radius: 10px;
    background: #FFF;
    background-repeat: no-repeat;
    background-position: 93% center;
    border: none;
    text-transform: uppercase;
    box-shadow: 0px 4px 8px rgba(54, 123, 245, 0.16), 0px 2px 4px rgba(54, 123, 245, 0.24);
    
}

.userpic {
    background: url('../assets/icons/userpic.png');
    width: 40px;
    height: 40px;
    background-repeat: no-repeat;
}

.subheader {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    height: 56px;
    padding-top: 0;
    padding-bottom: 0;
    padding-right: 16px;
    padding-left: 375px;
    background: #FFF;
/*    border-bottom: 1px solid gray;*/
}

.tabs-container {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
}

.tab {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    display: flex;
    align-items: center;
    justify-content: center;
    letter-spacing: 0.44px;
    color: #5E6366;
    padding: 10px;
    border: 1px solid white;
    border-radius: 8px ;
}

.tab-active {
    color: #000;
    border: 1px solid lightgray;
}

.dashboard-container {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: flex-start;
    width: 100%;
    height: 454px;
/*    border: 1px solid gray;*/
}

.dashboard-container__controls {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    width: 375px;
    height: 100%;
/*    border: 1px solid green;*/
    padding-top: 32px;

}

.create-button {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    background: #FFFFFF;
    box-shadow: 0px 16px 24px rgba(54, 123, 245, 0.16), 0px 6px 12px rgba(54, 123, 245, 0.16);
    border-radius: 99px;
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
    letter-spacing: 0.15px;
    color: #367BF5;
    background: url('../assets/icons/icon-add.png'), #FFF;
    background-repeat: no-repeat;
    background-position: 10% center;
    border: none;
    width: 213px;
    height: 56px;
    margin-bottom: 24px;

}

.dashboard-container__controls__row {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 260px;
    height: 56px;
/*    border: 1px solid gray;*/
    padding: 5px 10px;
    cursor: pointer;
}

.icon1 {
    background: url('../assets/icons/icon1.png');
    background-repeat: no-repeat;
    width: 20px;
    height: 20px;
}

.icon2 {
    background: url('../assets/icons/icon2.png');
    background-repeat: no-repeat;
    width: 24px;
    height: 20px;
}

.icon3 {
    background: url('../assets/icons/icon3.png');
    background-repeat: no-repeat;
    width: 28px;
    height: 28px;
}

.dashboard-container__controls__row__right {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    margin-left: 12px;
    margin-bottom: 8px;
}

.controls-title {
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0.44px;
    color: rgba(0, 0, 0, 0.87);
    font-family: 'Roboto';
}

.controls-subtitle {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 16px;
    letter-spacing: 0.4px;
    color: #5E6366;
}

.dashboard-container__table {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    width: 1065px;
    height: 100%;
/*    border: 1px solid green;*/
    padding-top: 32px;
    padding-right: 120px;

}

.dashboard-container__table__row {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}

.table-header {
    font-style: normal;
    font-weight: 500;
    font-size: 34px;
    line-height: 42px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    font-family: 'Roboto';
}

.table-right {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    gap: 8px;
}

.table-date {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    height: 32px;
    padding: 0 7px;
    border: 1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    border-radius: 10px;
}

.table-print {
    background: url('../assets/icons/icon-print.png'), white;
    background-repeat: no-repeat;
    width: 32px;
    height: 32px;
    background-position: center;
    border-radius: 3px;
}

.table-download {
    background: url('../assets/icons/icon-download.png'), white;
    background-repeat: no-repeat;
    width: 32px;
    height: 32px;
    background-position: center;
    border-radius: 3px;
}

.table-dashboard {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
/*    border: 1px solid red;*/
    width: 935px;
}

.table-dashboard__row:nth-child(1).standart-row {
    color: red;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
    letter-spacing: 0.15px;
    color: rgba(0, 0, 0, 0.87);
}

.table-dashboard__row {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    height: 64px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 28px;
    letter-spacing: 0.15px;
    color: rgba(0, 0, 0, 0.87);

}

.table-dashboard__row:nth-child(1) {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    height: 64px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0.44px;
    color: #919699;

}

.table-dashboard__row__col {
    display: flex;
    align-items: center;
    padding: 0 10px;

}

.table-dashboard__row__col:nth-child(1) {
    width: 330px;
    justify-content: flex-start;
}

.table-dashboard__row__col:nth-child(2) {
    width: 121px;
    justify-content: flex-end;
}

.table-dashboard__row__col:nth-child(3) {
    width: 121px;
    justify-content: flex-end;
}

.table-dashboard__row__col:nth-child(4) {
    width: 121px;
    justify-content: flex-end;
}

.table-dashboard__row__col:nth-child(5) {
    width: 121px;
    justify-content: flex-end;
}

.table-dashboard__row__col:nth-child(6) {
    width: 121px;
    justify-content: flex-end;
}

.search-field {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 0 7px;
    border:1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    width: 100%;
    height: 32px;
    border-radius: 10px;
}

.search1 {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 0 7px;
    border:1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    width: 100%;
    height: 32px;
    border-radius: 10px;
    width: 86px;
}

.search2 {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 0 7px;
    border:1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    width: 100%;
    height: 32px;
    border-radius: 10px;
    width: 86px;
}

.search3 {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 0 7px;
    border:1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    width: 100%;
    height: 32px;
    border-radius: 10px;
    width: 86px;
}

.search4 {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 0 7px;
    border:1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    width: 100%;
    height: 32px;
    border-radius: 10px;
    width: 86px;
}

.search5 {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    padding: 0 7px;
    border:1px solid lightgray;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.25px;
    color: rgba(0, 0, 0, 0.87);
    width: 100%;
    height: 32px;
    border-radius: 10px;
    width: 86px;
}
</style>
