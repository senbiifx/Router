<p><strong>Usage</strong></p>
<p>&nbsp;</p>
<p><strong>The App Root</strong></p>
<p>App root pertains to the container where the contents will be displayed.</p>
<blockquote>
<p>FXRouter.<em>appRoot</em>(stackPane);</p>
</blockquote>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Bindings</strong></p>
<p>Bind names to fxmls. These names will be used to navigate between views.</p>
<blockquote>
<p>&nbsp;FXRouter.<em>when</em>("select", "/selectView.fxml");</p>
<p>&nbsp; FXRouter.<em>when</em>("result", "/resultView.fxml");</p>
</blockquote>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><strong>Navigation</strong></p>
<p>Simply call:</p>
<blockquote>
<p>FXRouter.<em>goTo</em>("result");</p>
</blockquote>
<p>&nbsp;</p>
<p>The <em>goTo</em> method actually returns the controller of that specific fxml view. Use it when you want to call the methods of the controller.</p>
<p>&nbsp;</p>
<p><strong>Parameterized Navigation</strong></p>
<p>&nbsp;</p>
<p>What if we need to pass parameters upon navigating? Suppose we need to pass a date object. We can use the same method <em>goTo</em>:</p>
<p>&nbsp;</p>
<blockquote>
<p>&nbsp; &nbsp; Date date = <strong>new</strong> Date();</p>
<p>&nbsp; &nbsp; FXRouter.<em>goTo</em>("select", Param.<em>name</em>("dateToday")</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; .inject(date));</p>
</blockquote>
<p><em>&nbsp;</em></p>
<p>&nbsp;</p>
<p>This is how the destination controller would accept the date parameter:</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p>
<blockquote>
<p><strong>public</strong> <strong>class</strong> <u>ResultController</u> {</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @RoutingSetup</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>private</strong> <strong>void</strong> setup(@Var("dateToday") Date date) {</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; //do whatever you want here</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</p>
<p>}</p>
</blockquote>
