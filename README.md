# Tech-Acadamy-Projects
This is my Tech Academy for Learning Purposes

/*styling list points*/
ul {
    list-style: disc;
    margin: 0 0 1.5em 1em;
}

/*Positioning of icons*/
.social-media{
    padding: 0;
    margin: 30px 0 0;
    list-style-type: none;
    float: right;
}

.social-media li{
    display: inline-block;
    margin: 1px;
    vertical-align: bottom;
}

/*Styling the icons.*/
.social-media li a, i {
    background: #9D7C39;
    width: 30px;
    display: block;
    height: 30px;
    text-align: center;
    color: #FFFBFB;
    padding-top: 5px;
    border-radius: 100%;
    font-size: 16px;
    margin-right: 20px;
    top: auto;
}

/*hover affect for icons*/
.social-media li a:hover {
    background: #FFFBFB;
}

.copy-right {
    padding: 25px 0 25px 0;
    background: #000000;
    bottom: 0;
}

footer{
    height: 1.5rem;
    width: 100%;
    bottom: 0;
    display: block;
    position: absolute;
}

.footer-text {
    color: #FFFBFB;
    bottom: 0;
    padding: 35px;
}
Created a Card 
<head>
<link rel="stylesheet" href="~/Content/Site.css" />
<link rel="stylesheet" href="~/Content/bootstrap.css" />
</head>

<div class="card" style="width: 18rem;">
  <img class="card-img-top" src="" alt="">
  <div class="card-body">
    <h5 class="card-title">Text about user's card</h5>
    <p class="card-text">A place to put information.</p>
    <a href="#" class="btn btn-secondary">A button to take you to another page.</a>
  </div>
</div>
Created a Photo Model to store data
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.ComponentModel.DataAnnotations;

namespace TheatreCMS2.Models
{
    public class Photo
    {
        public int PhotoId { get; set; }
        public int PhotoFile { get; set; }
        public int OriginalHeight { get; set; }
        public int OriginalWidth { get; set; }
        public string Title { get; set; }

    }
}
Create a CRUD functionality for Photos. 
@model TheatreCMS2.Models.Photo

@{
    ViewBag.Title = "Create";
}

<h2>Create</h2>

@using (Html.BeginForm()) 
{
    @Html.AntiForgeryToken()
    
    <div class="form-horizontal">
        <h4>Photo</h4>
        <hr />
        @Html.ValidationSummary(true, "", new { @class = "text-danger" })
        <div class="form-group">
            @Html.LabelFor(model => model.PhotoFile, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.PhotoFile, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.PhotoFile, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.OriginalHeight, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.OriginalHeight, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.OriginalHeight, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.OriginalWidth, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.OriginalWidth, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.OriginalWidth, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Title, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Title, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.Title, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            <div class="col-md-offset-2 col-md-10">
                <input type="submit" value="Create" class="btn btn-default" />
            </div>
        </div>
    </div>
}

<div>
    @Html.ActionLink("Back to List", "Index")
</div>
@model TheatreCMS2.Models.Photo

@{
    ViewBag.Title = "Delete";
}

<h2>Delete</h2>

<h3>Are you sure you want to delete this?</h3>
<div>
    <h4>Photo</h4>
    <hr />
    <dl class="dl-horizontal">
        <dt>
            @Html.DisplayNameFor(model => model.PhotoFile)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.PhotoFile)
        </dd>

        <dt>
            @Html.DisplayNameFor(model => model.OriginalHeight)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.OriginalHeight)
        </dd>

        <dt>
            @Html.DisplayNameFor(model => model.OriginalWidth)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.OriginalWidth)
        </dd>

        <dt>
            @Html.DisplayNameFor(model => model.Title)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.Title)
        </dd>

    </dl>

    @using (Html.BeginForm()) {
        @Html.AntiForgeryToken()

        <div class="form-actions no-color">
            <input type="submit" value="Delete" class="btn btn-default" /> |
            @Html.ActionLink("Back to List", "Index")
        </div>
    }
</div>
@model TheatreCMS2.Models.Photo

@{
    ViewBag.Title = "Details";
}

<h2>Details</h2>

<div>
    <h4>Photo</h4>
    <hr />
    <dl class="dl-horizontal">
        <dt>
            @Html.DisplayNameFor(model => model.PhotoFile)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.PhotoFile)
        </dd>

        <dt>
            @Html.DisplayNameFor(model => model.OriginalHeight)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.OriginalHeight)
        </dd>

        <dt>
            @Html.DisplayNameFor(model => model.OriginalWidth)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.OriginalWidth)
        </dd>

        <dt>
            @Html.DisplayNameFor(model => model.Title)
        </dt>

        <dd>
            @Html.DisplayFor(model => model.Title)
        </dd>

    </dl>
</div>
<p>
    @Html.ActionLink("Edit", "Edit", new { id = Model.PhotoId }) |
    @Html.ActionLink("Back to List", "Index")
</p>
@model TheatreCMS2.Models.Photo

@{
    ViewBag.Title = "Edit";
}

<h2>Edit</h2>

@using (Html.BeginForm())
{
    @Html.AntiForgeryToken()
    
    <div class="form-horizontal">
        <h4>Photo</h4>
        <hr />
        @Html.ValidationSummary(true, "", new { @class = "text-danger" })
        @Html.HiddenFor(model => model.PhotoId)

        <div class="form-group">
            @Html.LabelFor(model => model.PhotoFile, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.PhotoFile, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.PhotoFile, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.OriginalHeight, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.OriginalHeight, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.OriginalHeight, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.OriginalWidth, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.OriginalWidth, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.OriginalWidth, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Title, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Title, new { htmlAttributes = new { @class = "form-control" } })
                @Html.ValidationMessageFor(model => model.Title, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            <div class="col-md-offset-2 col-md-10">
                <input type="submit" value="Save" class="btn btn-default" />
            </div>
        </div>
    </div>
}

<div>
    @Html.ActionLink("Back to List", "Index")
</div>
@model IEnumerable<TheatreCMS2.Models.Photo>

@{
    ViewBag.Title = "Index";
}

<h2>Index</h2>

<p>
    @Html.ActionLink("Create New", "Create")
</p>
<table class="table">
    <tr>
        <th>
            @Html.DisplayNameFor(model => model.PhotoFile)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.OriginalHeight)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.OriginalWidth)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.Title)
        </th>
        <th></th>
    </tr>

@foreach (var item in Model) {
    <tr>
        <td>
            @Html.DisplayFor(modelItem => item.PhotoFile)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.OriginalHeight)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.OriginalWidth)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.Title)
        </td>
        <td>
            @Html.ActionLink("Edit", "Edit", new { id=item.PhotoId }) |
            @Html.ActionLink("Details", "Details", new { id=item.PhotoId }) |
            @Html.ActionLink("Delete", "Delete", new { id=item.PhotoId })
        </td>
    </tr>
}

</table>
