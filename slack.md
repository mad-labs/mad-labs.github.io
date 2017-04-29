---
layout: default
---
<style>
    #slack-signup-wrapper{
        position:relative;
        width:100%;
        height:300px;
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

<section class="wrapper spreadbytes special fade-up">
	<div class="content">
		 <header class="major">
			<h2>Mad Labs - Slack channel</h2>
		</header>
		<p>We got a slack channel too! You are free to join us and take part of our discussions about web development!</p>
		<div id="slack-signup-wrapper">
			<div class="flexcontainer"><iframe src="https://slackin-mad-labs.herokuapp.com/" id="slack-signup" scrolling="no"></iframe></div>
		</div>
	</div>
</section>
