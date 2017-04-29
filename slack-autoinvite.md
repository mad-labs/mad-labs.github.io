---
layout: default
---

<style>
    #slack-signup-wrapper{
        position:relative;
        width:100%;
        height:300px;
        margin-top:100px;
        background-color:white;
        overflow:hidden
    }
    #slack-signup{
        position:absolute;
        top:-175px;
        left:0;
        width:100%;
        height:500px;
        margin:0;
        padding:0;
        border:0;
    }
    @media all and (max-width:380px){
        #slack-signup-wrapper{
            height:250px
        }
        #slack-signup{
            left:-20px;
            top:-150px;
            width:120%
        }
    }

    .flexcontainer {
        margin-top: 100px;
        display: -webkit-flex;
        display: flex;
        -webkit-flex-direction: row /* works with row or column */
        flex-direction: row;
        -webkit-align-items: center;
        align-items: center;
        -webkit-justify-content: center;
        justify-content: center;
    }

</style>
<div id="slack-signup-wrapper">
    <div class="flexcontainer"><iframe src="https://slackin-mad-labs.herokuapp.com/" id="slack-signup" scrolling="no"></iframe></div>
</div>

