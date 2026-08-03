<grid drag="100 10" drop="top" bg="white" align="left" pad="0 20px" class="slide-title">
 <% title %>
</grid>

<grid drag="28 75" drop="69 15" bg="white" style="border-radius:15px"/>

<grid drag="50 70" drop="0 10" align="topleft">
<% left %>
</grid>

<grid drag="50 71" drop="50 10" align="topleft" class="right-panel">
<% right %>
</grid>

<% content %>

<style>
.horizontal_dotted_line {
  border-bottom: 2px dotted gray;
}

/* Footer text smaller */
.footer-text {
  font-size: 12px;
  color: gray;
  text-align: right;
}

/* Right-hand side smaller */
.right-panel {
  font-size: 14px;
  line-height: 1.2;
}

/* Slide title smaller, not italic, normal case, less margin below */
.slide-title {
  font-size: 28px;         /* adjust as needed */
  font-style: normal;      /* remove italics */
  margin-bottom: 5px;      /* reduce space between title and body */
  text-transform: none;    /* normal capitalization */
}
</style>


<grid drag="100 30" drop="0 80" align="bottomleft" pad="0 30px" >
<%? source %>
</grid>

<grid drag="100 6" drop="bottom" class="footer-text">
###### <%? date %> 
</grid>

