<grid drag="100 10" drop="top" bg="white" align="left" pad="0 20px" class="slide-title">
 <% title %>
</grid>

<grid drag="25 40" drop="0 10" align="topleft">
<% top1 %>
</grid>

<grid drag="25 40" drop="25 10" align="topleft">
<% top2 %>
</grid>

<grid drag="25 40" drop="50 10" align="topleft">
<% top3 %>
</grid>

<grid drag="25 40" drop="75 10" align="topleft">
<% top4 %>
</grid>

<grid drag="25 40" drop="0 50" align="topleft">
<% bottom1 %>
</grid>

<grid drag="25 40" drop="25 50" align="topleft" >
<% bottom2 %>
</grid>

<grid drag="25 40" drop="50 50" align="topleft">
<% bottom3 %>
</grid>

<grid drag="25 40" drop="75 50" align="topleft">
<% bottom4 %>
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

<grid drag="94 0" drop="3 -6" class="horizontal_dotted_line">
</grid>

<grid drag="100 30" drop="0 64" align="bottomleft" pad="0 30px" >
<%? source %>
</grid>

<grid drag="100 6" drop="bottom" class="footer-text">
#### <%? date %>  Ida Wöstheinrich
</grid>

