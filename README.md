# Blogging_API_using_NodeJS_GCF_MongoDB

API to perform CRUD operations on blogs. <br/>
The API server is created using NodeJS and deployed as a GCF ( Google Cloud Function ). The blogs are stored in MongoDB.
<br/><br/>
<p><strong>Blogging API Documentation:</strong></p>
<p><strong>/</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/</span></a></p>
<p><strong>Methods allowed:</strong><span style="font-weight: 400;"> Any</span></p>
<p><strong>Description: </strong><span style="font-weight: 400;">The base url of the GCF function which contains all the Blogging APIs.</span></p>
<p><strong>Response:</strong></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 200 &nbsp; </span> <span style="font-weight: 400;">Specify any resource in the url</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 404</span> <span style="font-weight: 400;">Resource {resource in url} not found. Enter a valid path</span></p>
<p>&nbsp;</p>
<p><strong>/getBlogs</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/getBlogs"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/getBlogs</span></a></p>
<p><strong>Methods allowed:</strong><span style="font-weight: 400;"> GET or POST&nbsp;</span></p>
<p><strong>Description:</strong><span style="font-weight: 400;"> Returns the search result of documents satisfying the parameters. If you pass the content field, the search index will be used. Otherwise, normal indexes will be used.</span></p>
<p><strong>Parameters:</strong><span style="font-weight: 400;"> ( can be passed&nbsp; in the body of the post request or in the query string in the url )&nbsp;</span></p>
<ol>
<li style="font-weight: 400;"><span style="font-weight: 400;">author&nbsp;</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">title</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">content</span></li>
</ol>
<p><strong>Response:</strong></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 200 &nbsp; </span> <span style="font-weight: 400;">List of blogs matching the search query</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 204 &nbsp; </span> <span style="font-weight: 400;">There are no blogs matching the search query</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 400 &nbsp; </span> <span style="font-weight: 400;">Bad Request</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 405 &nbsp; </span> <span style="font-weight: 400;">Method Not Allowed</span></p>
<p><strong>Example:</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/getBlogs?author=John&amp;content=document"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/getBlogs?author=John&amp;content=document</span></a></p>
<p>&nbsp;</p>
<p><strong>/postBlog</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/postBlog"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/postBlog</span></a></p>
<p><strong>Methods allowed:</strong><span style="font-weight: 400;"> PUT or POST&nbsp;</span></p>
<p><strong>Description:</strong><span style="font-weight: 400;"> Creates a blog post containing the fields in the parameters.</span></p>
<p><strong>Parameters:</strong><span style="font-weight: 400;">&nbsp; ( can be passed in the body of the post request or in the query string in the url )&nbsp;</span></p>
<ol>
<li style="font-weight: 400;"><span style="font-weight: 400;">author&nbsp;</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">title ( unique , required )</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">content</span></li>
</ol>
<p><strong>Response:</strong></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 201 &nbsp; </span> <span style="font-weight: 400;">Blog {title passed in parameters} has been posted Successfully</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 400 &nbsp; </span> <span style="font-weight: 400;">Bad Request</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 403</span> <span style="font-weight: 400;">Title value must be unique. A blog with the title {title passed in parameters} already exists</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 405 &nbsp; </span> <span style="font-weight: 400;">Method Not Allowed</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 449</span> <span style="font-weight: 400;">Title field is required</span></p>
<p><strong>Example:</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/postBlog?author=John&amp;title=document1&amp;content=document1"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/postBlog?author=John&amp;title=document1&amp;content=document1</span></a></p>
<p>&nbsp;</p>
<p><strong>/updateBlog</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/updateBlog"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/updateBlog</span></a></p>
<p><strong>Methods allowed:</strong><span style="font-weight: 400;">&nbsp; POST&nbsp;</span></p>
<p><strong>Description:</strong><span style="font-weight: 400;"> Updates the blog containing the specified title with the new values in the parameters</span></p>
<p><strong>Parameters:</strong><span style="font-weight: 400;">&nbsp; ( can be passed in the body of the post request or in the query string in the url )&nbsp;</span></p>
<ol>
<li style="font-weight: 400;"><span style="font-weight: 400;">author&nbsp;</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">title ( required )</span></li>
<li style="font-weight: 400;"><span style="font-weight: 400;">content</span></li>
</ol>
<p><strong>Response:</strong></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 200 &nbsp; </span> <span style="font-weight: 400;">The Blog {title passed in parameters} has been updated Successfully</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 400 &nbsp; </span> <span style="font-weight: 400;">Bad Request</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 403</span> <span style="font-weight: 400;">No blog with the specified title {title passed in parameters} exists</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 405 &nbsp; </span> <span style="font-weight: 400;">Method Not Allowed</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 449</span> <span style="font-weight: 400;">Title field is required</span></p>
<p><strong>Example:</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/updateBlog?title=document2&amp;content=updated"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/updateBlog?title=document2&amp;content=updated</span></a></p>
<p>&nbsp;</p>
<p><strong>/deleteBlog</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/Stackruit_Blogs/deleteBlog"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/deleteBlog</span></a></p>
<p><strong>Methods allowed:</strong><span style="font-weight: 400;"> POST&nbsp;</span></p>
<p><strong>Description:</strong><span style="font-weight: 400;"> Deletes the blog containing the specified title</span></p>
<p><strong>Parameters:</strong><span style="font-weight: 400;">&nbsp; ( can be passed in the body of the post request or in the query string in the url )&nbsp;</span></p>
<ol>
<li style="font-weight: 400;"><span style="font-weight: 400;">title ( required )</span></li>
</ol>
<p><strong>Response:</strong></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 200 &nbsp; </span> <span style="font-weight: 400;">The Blog {title passed in parameters} has been deleted successfully</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 400 &nbsp; </span> <span style="font-weight: 400;">Bad Request</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 403</span> <span style="font-weight: 400;">No blog with the specified title {title passed in parameters} exists</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 405 &nbsp; </span> <span style="font-weight: 400;">Method Not Allowed</span></p>
<p><strong>Status:</strong><span style="font-weight: 400;"> 449</span> <span style="font-weight: 400;">Title field is required</span></p>
<p><strong>Example:</strong></p>
<p><a href="https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/deleteBlog?title=document2"><span style="font-weight: 400;">https://asia-south1-stackruit-assessment.cloudfunctions.net/blogs/deleteBlog?title=document2</span></a></p>
<p>&nbsp;</p>
