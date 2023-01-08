<script>
  let regexString = '';
  /**
	 * @type {RegExp | null}
	 */
  let regex = RegExp("^(?!\s*$).+");
  let input = '';
  let message = '';
  let icon = '';
  let success = false;

 $: try {
    regex = new RegExp(regexString);
  } catch (e) {
    message = 'Error: Invalid regular expression';
    icon = '❌';
  }

   $: if (!regexString) {
    message = 'Please enter a regular expression';
    icon = '';
  } else if (!input) {
    message = 'Please enter a string to test';
    icon = '';
  } else if (!regex) {
    // Do nothing
  } else if (regex.test(input)) {
    message = 'Success! String Matches';
    icon = '🎉';
    success = true;
  } else {
    message = 'Does Not Match';
    icon = '❌';
  }

//  // @ts-ignore
//    $: if (success && !regex.test(input)) {
//     message = 'Error: Regular expression has changed';
//     icon = '❌';
//   }
</script>

<p>Regular Expression</p>
<div class="form1">
  <div class="input-group"></div>
    <textarea bind:value={regexString} name="text" cols="40" rows="5" placeholder="Write your regex expression here.."></textarea>

</div>
<div class="empty">
	<h2 class:error={message.startsWith('Does Not Match')} class:success={message === 'Success! String Matches'}>{icon} {message}</h2>
</div>
<div class="form2"><textarea bind:value={input} name="text" cols="40" rows="5" placeholder="Write your string to test here.."></textarea></div>

<style>
  ::placeholder {
    color: rgba(0, 0, 0, 0.678);
  }
    .error {
    color: red;
  }
  .success {
    color: green;
  }
.empty{
	height: 80px;
	margin: auto;
	display: flex;
 align-items: center;
 justify-content: center;
}
  textarea {
      height: 100%;
	  color: black;
	  border: none;
    outline: none;
	resize: none;
	border-radius: 15px;
	padding: 5px;
    width: 100%;
   -webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
    -moz-box-sizing: border-box;    /* Firefox, other Gecko */
    box-sizing: border-box;
  }
  p {

    width: 317px;
    height: 73px;
    left: 316px;
    top: 156px;
	margin: auto;
    font-family: "Patrick Hand SC";
    font-style: normal;
    font-weight: 400;
    font-size: 40px;
    line-height: 54px;
    text-align: center;

    color: #ffffff;
  }
  .form1 {

    width: 80%;
    height: 113px;
    left: 334px;
    top: 219px;
	margin: auto;
  }
  .form2 {

    width: 80%;
    height: 200px;
    left: 334px;
    top: 381px;
    margin: auto;
  }
</style>
