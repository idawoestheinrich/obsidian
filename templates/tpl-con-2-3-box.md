<grid drag="100 10" drop="top" bg="white" align="left" pad="0 20px" class="slide-title">
 <% title %>
</grid>

<grid drag="30 35" drop="0 10" align="topleft">
<% top1 %>
</grid>

<grid drag="30 35" drop="33 10" align="topleft">
<% top2 %>
</grid>

<grid drag="30 35" drop="66 10" align="topleft">
<% top3 %>
</grid>


<grid drag="30 35" drop="0 50" align="topleft">
<% bottom1 %>
</grid>

<grid drag="30 35" drop="33 50" align="topleft" >
<% bottom2 %>
</grid>

<grid drag="30 35" drop="66 50" align="topleft">
<% bottom3 %>
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

<grid drag="100 30" drop="0 64" align="bottomleft" pad="0 30px" >
<%? source %>
</grid>

