<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Employee System</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css">
    <link rel="stylesheet" href="css/style.css">
    <link href="https://gitcdn.github.io/bootstrap-toggle/2.2.2/css/bootstrap-toggle.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/toastr.min.css">
    <link rel="stylesheet" href="css/jquery-ui.min.css"/>
    <link href="http://cdnjs.cloudflare.com/ajax/libs/summernote/0.8.11/summernote.css" rel="stylesheet">
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <link rel="stylesheet" href="/resources/demos/style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <!--multiselect-->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-multiselect/0.9.15/css/bootstrap-multiselect.css">
    <link href="https://cdn.datatables.net/1.10.19/css/jquery.dataTables.min.css" rel="stylesheet"/>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto|Varela+Round">
    <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">



    <!--<script src="https://code.jquery.com/jquery-3.3.1.js"></script>-->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/js/bootstrap.min.js"></script>
    <script src="js/scripts.js" type="text/javascript"></script>
    <script src="js/validation.js" type="text/javascript"></script>
    <script src="js/data.js" type="text/javascript"></script>
    <script src="https://gitcdn.github.io/bootstrap-toggle/2.2.2/js/bootstrap-toggle.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/latest/toastr.min.js"></script>
    <script src="http://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/summernote/0.8.11/summernote.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-multiselect/0.9.15/js/bootstrap-multiselect.js"></script>
    <script src="https://cdn.datatables.net/1.10.19/js/jquery.dataTables.min.js"></script>
    <!--<script src="https://cdn.datatables.net/1.10.19/js/dataTables.bootstrap.min.js"></script>-->

    <script>
        $( function() {
            $( ".sortable" ).sortable();
            $( ".sortable" ).disableSelection();
        });
    </script>
</head>
<div class="container"style="margin-top:30px">
    <div class="row">
        <div class="col-lg-10 header">
            <b><span id="dateTime"></span></b>
            <span class="sessionData" style="float: right"></span>
          <h2>Employee Management System</h2>
        </div>
    </div>
    <div class="row">
        <div class="col-md-12 col-sm-2 col-md-2 content-left">
            <ul class="nav nav-tabs tabs-left sideways">
                <li><a href="#login-v" data-toggle="tab">Login</a></li>
                <li><a href="#register-v"  data-toggle="tab">Register</a></li>
                <li><a href="#employee-v" id="displayEmp" data-toggle="tab">Employee</a></li>
                <li><a href="#changePassword-v" data-toggle="tab">Change Password</a></li>
                <li><a href="#logout-v"  id="logout" data-toggle="tab">Log out</a></li>
            </ul>
        </div>
        <div class="col-md-12 col-sm-10 col-md-10 content-right">
            <div class="tab-content">
                <div class="tab-pane" id="login-v">
                    <form id="login_form" class="validation_login" name="login_form" method="post" action="">
                            <div class="panel panel-default">
                                <div class="panel-heading">
                                    <h3 class="panel-title">
                                        <strong>Login</strong>
                                    </h3>
                                </div>
                                <div class="panel-body">
                                        <div class="row">
                                            <div class="col-xs-12 col-sm-12 col-md-12">
                                                <div class="form-group">
                                                    <div class="input-group">
                                                        <span class="input-group-addon"><i class="glyphicon glyphicon-user"></i></span>
                                                        <input type="email" email-check="Please Enter valid Email" name="email_id" errorMessage="Enter value in Email" id="email_id" class="form-control check-valid" placeholder="Enter Email Id" tabindex="1">
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="row">
                                            <div class="col-xs-12 col-sm-12 col-md-12">
                                                <div class="form-group">
                                                    <div class="input-group">
                                                        <span class="input-group-addon"><i class="glyphicon glyphicon-lock"></i></span>
                                                        <input type="password" name="user_password" errorMessage="Enter value in Password" id="user_password"  placeholder="Enter Password" class="form-control check-valid" tabindex="2">
                                                    </div>
                                                    <span id="user_password_error"></span>
                                                </div>
                                            </div>
                                        </div>
                                           <button type="button" id="login" name="login" class="btn btn-success">Login</button>
                                             <hr style="margin-top:10px;margin-bottom:10px;">
                                </div>
                            </div>
                    </form>
                </div>
                <div class="tab-pane" id="register-v">
                    <form id="register_form" name="register_form" class="validation_register" method="post" action="">
                        <!--<div class="col-md-10">-->
                        <div class="panel panel-default">
                            <div class="panel-heading">
                                <h3 class="panel-title">
                                    <strong>Register</strong>
                                </h3>
                            </div>
                            <div class="panel-body">
                                <div class="row">
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-user"></i></span>
                                                <input type="text" name="first_name" errorMessage="Enter value in First name" id="first_name" class="form-control check-valid"  errorMessage="Enter value in First name" placeholder="First Name" tabindex="1">
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-user"></i></span>
                                                <input type="text" name="middle_name" id="middle_name" class="form-control check-valid" isvalidate = "true" errorMessage="Enter value in Middle name"placeholder="Middle Name" tabindex="2">
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-user"></i></span>
                                                <input type="text" name="last_name"  errorMessage="Enter value in Last name" id="last_name" class="form-control check-valid" placeholder="Last Name" tabindex="3">
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-envelope"></i></span>
                                                <input type="email" name="email" email-check="Please Enter valid Email"  errorMessage="Enter value in Email" id="email" class="form-control check-valid" placeholder="Email Address" tabindex="4">
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-eye-close"></i></span>
                                                <input type="password" name="password"  errorMessage="Enter value in Password" id="password" class="form-control check-valid" placeholder="Password" tabindex="5">
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-eye-close"></i></span>
                                                <input type="password" name="password_confirmation"  errorMessage="Enter value in Confirm Password" id="password_confirmation" class="form-control check-valid" placeholder="Confirm Password" tabindex="6">
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                        <div class="form-group">
                                            <div class="input-group">
                                                <span class="input-group-addon"><i class="glyphicon glyphicon-home"></i></span>
                                                <select name="roles" errorMessage="Select value in Roles" id="roles" class="form-control check-valid" tabindex="8">
                                                    <option value="">Select roles</option>
                                                    <option value="User">User</option>
                                                    <option value="Admin">Admin</option>
                                                </select>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-xs-12 col-sm-6 col-md-6">
                                                <div class="file btn btn-sm btn-info file-btn">
                                                    Upload
                                                    <input type="file" name="file" id="file-upload"class="check-valid" errorMessage="Choose profile"/>
                                                </div>
                                                <div class="image-container">
                                                    <img src="" id="image-preview"  />
                                                    <button type="button" class="close" aria-label="Close" style="display: none">
                                                        <span aria-hidden="true">&times;</span>
                                                    </button>
                                                </div>
                                        <div class="localstorage-output"></div>

                                        </div>
                                </div>
                                <input type="button" id="register" name="register" class="btn btn-success" value="Register"/>
                                <hr style="margin-top:10px;margin-bottom:10px;">
                            </div>
                        </div>
                        <!--</div>-->
                    </form>
                </div>
                <div class="tab-pane" id="employee-v">
                    <form id="Employee_form" name="Employee_form" method="post" action="">
                        <!--<div class="col-md-10">-->
                        <div class="panel panel-default">
                            <div class="panel-heading">
                                <h3 class="panel-title">
                                    <strong>Employee Details </strong>
                                </h3>
                            </div>
                            <div class="panel-body">
                                <div class="row">
                                    <div class="col-xs-12 col-sm-12 col-md-12">
                                        <a type="button" href="#EmployeeModal" data-toggle="modal" id="Employee" name="Employee" class="btn btn-primary">New</a>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-xs-12 col-sm-12 col-md-12 Display-div">

                                        <!--<button type="button" id="addEmployee"><i class="fa fa-plus-square" style="font-size:25px;"></i></i></button>-->
                                        <table border='1' id='Empdatatable' class='table table-bordered table-striped table-hover'>
                                            <thead>
                                                <tr>
                                                    <th style="visibility: hidden">Id</th>
                                                    <th style="display: none"></th>
                                                    <th>First Name</th>
                                                    <th>Last Name</th>
                                                    <th>DOB</th>
                                                    <th>Designation</th>
                                                    <th>Email</th>
                                                    <!--<th>Skill</th>-->
                                                    <th>Country</th>
                                                    <th>Relationship</th>
                                                    <th></th>
                                                </tr>
                                            </thead>
                                        </table>

                                    </div>
                                </div>
                                    <hr style="margin-top:10px;margin-bottom:10px;">
                            </div>
                        </div>
                    </form>

                </div>
                <div class="tab-pane" id="changePassword-v">Password Tab.</div>
                <div class="tab-pane" id="logout-v">
                    <div style="display: none" id="display-logout" class="alert alert-success alert-dismissible fade in">
                        <a href="#" class="close" data-dismiss="alert" aria-label="close">&times;</a>
                        <strong>Logout Successfully!</strong>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="row">
        <div class="col-lg-12 footer">
            footer
        </div>
    </div>
</div>
 <div id="EmployeeModal" class="modal fade">
        <div class="modal-dialog">
            <div class="modal-content">
                    <div class="modal-header">
                        <h4 class="modal-title">Add Employee Details</h4>
                    </div>
                    <div class="modal-body">
                        <form class="empValidation" method="post" enctype="multipart/form-data">
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>First Name</label>
                                        <input type="hidden" id="empid" name="empid" class="form-control" >
                                        <input type="text" id="firstname" errorMessage="Enter value in First name" name="firstname" class="form-control check-valid" placeholder="Enter first name" tabindex="1">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Middle Name</label>
                                        <input type="text" id="middlename" errorMessage="Enter value in Middle name" name="middlename" class="form-control check-valid" placeholder="Enter middle name" tabindex="2" >
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Last Name</label>
                                        <input type="text" id="lastname" errorMessage="Enter value in Last name" name="lastname" class="form-control check-valid" placeholder="Enter last name" tabindex="3">
                                    </div>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Date of Birth</label>
                                        <input type="text" name="datepicker" errorMessage="Enter value in DOB" readonly id="datepicker"  placeholder="Enter DOB" class="form-control check-valid" tabindex="4">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group" tabindex="5">
                                        <label>Gender</label><br/>
                                        <input type="radio" name="gender" id="gender1" value="Male" checked/>Male
                                        <input type="radio" name="gender" id="gender2" value="Female" />Female
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Designation</label>
                                        <select name="designation" id="designation"  errorMessage="Select value in Designation" class="form-control check-valid" tabindex="6">
                                            <option value="">Select designation</option>
                                            <option value="Trainee">Trainee</option>
                                            <option value="Jr.Developer">Jr.Developer</option>
                                            <option value="Sr.Developer">Sr.Developer</option>
                                            <option value="Project Manager">Project Manager</option>
                                            <option value="Team Leader">Team Leader</option>
                                        </select>
                                    </div>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <label>Profile</label><br/>
                                    <div class="file btn btn-sm btn-info file-btn">
                                        Upload
                                        <input type="file" name="file" id="profile-upload" class="check-valid" errorMessage="Choose profile"/>
                                    </div>
                                    <div class="image-container">
                                        <img src="" id="profile-preview"  />
                                        <button type="button" class="close-pic" aria-label="Close" style="display:none;float: right">
                                            <span aria-hidden="true">&times;</span>
                                        </button>
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>User role</label>
                                        <input type="text" id="user-role" readonly name="user-role" value="Employee" class="form-control check-valid">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Department</label>
                                        <select id="example-getting-started" multiple="multiple">
                                            <option value="HR" id="HR" name="chk">HR</option>
                                            <option value="Developer" id="Developer" name="chk">Developer</option>
                                            <option value="Designer" id="Designer" name="chk">Designer</option>
                                            <option value="Manager" id="Manager" name="chk">Manager</option>
                                            <option value="Trainee" id="Trainee" name="chk">Trainee</option>
                                            <option value="Sales" id="Sales" name="chk">Sales</option>
                                        </select>
                                    </div>

                                </div>
                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                    <label>Date of Joining</label>
                                    <input type="text" name="dateOfJoin" readonly id="dateOfJoin" errorMessage="select date of joining" placeholder="Enter Join" class="form-control check-valid" tabindex="7">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Email Id</label>
                                        <input type="email" id="emailid" name="email" class="form-control check-valid"errorMessage="Enter value in email" email-check="Please Enter valid Email" placeholder="Enter Email" tabindex="8">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Password</label>
                                        <input type="password" id="newpassword" name="newpassword" class="form-control check-valid" errorMessage="Enter value in Password" placeholder="Enter Password" tabindex="9">
                                    </div>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Address</label>
                                        <textarea id="address" name="address" errorMessage="Enter value in Address" class="form-control check-valid" placeholder="Enter Address" tabindex="9"></textarea>
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Skill</label>
                                        <input type="text" id="skill" name="skill" class="form-control check-valid " errorMessage="Enter value in Skill" placeholder="Enter Skill" tabindex="9" >
                                    </div>
                                    <div class="sortable">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label style="visibility: hidden"> Add</label>
                                        <button type="button" id="addSkill"><i class="fa fa-plus-square" style="font-size:25px;"></i></i></button>
                                    </div>
                                </div>

                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-12 col-md-12">
                                    <div class="form-group">
                                        <label>Description</label>
                                        <textarea id="summernote" name="summernote" class="form-control check-valid " errorMessage="Enter value in Description" placeholder="Enter Description" tabindex="10" ></textarea>
                                    </div>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Country</label>
                                        <select name="country" id="country" errorMessage="Select value in Country"class="form-control check-valid" tabindex="11">
                                            <option value="" selected="selected">-- Select Country --</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>State</label>
                                        <select name="state" id="state" errorMessage="Select value in State" class="form-control check-valid" tabindex="12">
                                            <option value="" selected="selected">-- Select State--</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>City</label>
                                        <select name="city" id="city" errorMessage="Select value in City" class="form-control check-valid" tabindex="13">
                                            <option value="" selected="selected">-- Select City--</option>
                                        </select>
                                    </div>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Mobile No</label>
                                        <input type="text" id="phno" name="phno" errorMessage="Enter value in Phone No" class="form-control check-valid"placeholder="Enter Phone No." tabindex="9">
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Zipcode</label>
                                        <select name="zipcode" id="zipcode" errorMessage="Enter value in Zipcode" placeholder="Enter Zipcode" class="form-control check-valid" tabindex="14">
                                            <option value="" selected="selected">-- Select Zipcode--</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="col-xs-12 col-sm-4 col-md-4">
                                    <div class="form-group">
                                        <label>Relationship</label>
                                        <input id="toggle-event" type="checkbox" data-on="Married" data-off="Single" data-toggle="toggle">
                                    </div>
                                </div>
                            </div>
                        </form>
                    </div>
                    <div class="modal-footer">
                        <input type="button" class="btn btn-default" data-dismiss="modal" value="Cancel">
                        <input type="button" id="addEmp" name="addEmp" class="btn btn-info" value="Add">
                        <input type="button" style="display: none" id="updateEmp" name="updateEmp" class="btn btn-info" value="Update">
                    </div>
            </div>
        </div>
    </div>
</body>
</html>
