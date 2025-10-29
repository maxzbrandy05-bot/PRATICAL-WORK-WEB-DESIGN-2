# PRATICAL-WORK-WEB-DESIGN-2
05DIT24F1027(MAXBRANDY BANTIN)


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bloom College - Student Registration Form</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
  
  <style>
    body {
      background-color: #f7f7f7;
      font-family: Arial, sans-serif;
    }
    form {
      background-color: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 600px;
      margin: 30px auto;
    }
    h2, h5 {
      text-align: center;
    }
    .form-section {
      margin-bottom: 20px;
    }
  </style>
</head>
<body>

  <form id="studentForm">
    <h2>BLOOM COLLEGE</h2>
    <h5>Student Registration Form</h5>
    <hr>

    <div class="form-section">
      <label>Student Image:</label>
      <input type="file" class="form-control" accept="image/*">
      <small>(less than 5 MB)</small>
    </div>

    <div class="form-section">
      <label>Student Name:</label>
      <input type="text" id="studentName" class="form-control" placeholder="Full name">
    </div>

    <div class="form-section">
      <label>Father's Name:</label>
      <input type="text" id="fatherName" class="form-control" placeholder="Father's full name">
    </div>

    <div class="form-section">
      <label>Mother's Name:</label>
      <input type="text" id="motherName" class="form-control" placeholder="Mother's full name">
    </div>

    <div class="form-section">
      <label>Gender:</label><br>
      <input type="radio" name="gender" value="Male"> Male
      <input type="radio" name="gender" value="Female"> Female
    </div>

    <div class="form-section">
      <label>Date of Birth:</label>
      <input type="date" class="form-control">
    </div>

    <div class="form-section">
      <label>Email:</label>
      <input type="email" id="email" class="form-control" placeholder="email@example.com">
    </div>

    <div class="form-section">
      <label>Level:</label>
      <select class="form-control">
        <option>PhD</option>
        <option>Master</option>
        <option>Bachelor</option>
        <option>Diploma</option>
      </select>
    </div>

    <div class="form-section">
      <label>Department:</label>
      <select class="form-control">
        <option>Computer Engineering</option>
        <option>Information Technology</option>
        <option>Business Administration</option>
      </select>
    </div>

    <div class="form-section">
      <label>Tel/Mobile:</label>
      <input type="tel" class="form-control" placeholder="01x-xxx xxxx">
    </div>

    <h5>Address</h5>
    <div class="form-section">
      <label>State:</label>
      <input type="text" class="form-control" placeholder="State">
    </div>

    <div class="form-section">
      <label>City:</label>
      <input type="text" class="form-control" placeholder="City">
    </div>

    <div class="form-section">
      <label>Postcode:</label>
      <input type="text" class="form-control" placeholder="Postcode">
    </div>

    <div class="text-center">
      <button type="submit" class="btn btn-primary">Register</button>
      <button type="reset" class="btn btn-secondary">Reset</button>
    </div>
  </form>

  <!-- Bootstrap Modal -->
  <div class="modal fade" id="successModal" tabindex="-1" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-content text-center p-3">
        <h4 class="modal-title">Success!</h4>
        <p>Your details have been saved!</p>
        <button class="btn btn-success" data-bs-dismiss="modal">OK</button>
      </div>
    </div>
  </div>

  <script>
    // (i) onBlur event
    document.getElementById("email").addEventListener("blur", function() {
      this.style.backgroundColor = "#f8d7da"; // Light red when unfocused
    });

    // (ii) onFocus event for email field
    document.getElementById("email").addEventListener("focus", function() {
      this.style.backgroundColor = "#d1e7dd"; // Light green when focused
    });

    // (iii) onChange event to convert to CAPS LOCK
    const fields = ["studentName", "fatherName", "motherName"];
    fields.forEach(id => {
      document.getElementById(id).addEventListener("change", function() {
        this.value = this.value.toUpperCase();
      });
    });

    // (iv) Show Bootstrap modal on submission
    document.getElementById("studentForm").addEventListener("submit", function(e) {
      e.preventDefault();
      const modal = new bootstrap.Modal(document.getElementById("successModal"));
      modal.show();
    });
  </script>
</body>
</html>
