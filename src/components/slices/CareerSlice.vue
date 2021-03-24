<template>
  <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
      <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 col-sm-12 mx-auto text-center">
        <form method="post">
          <div class="row">
            <div class="col-md-6">
                <div class="mb-3">
                    <input type="text" name="userName" class="form-control" placeholder="NAME" value="" required>
                </div>
                <div class="mb-3">
                    <input type="text" name="userPhone" class="form-control" placeholder="TELEPHONE" value="" required>
                </div>
            </div>
            <div class="col-md-6 text-md-start">
                <div class="mb-3">
                    <input type="text" name="userEmail" class="form-control" placeholder="EMAIL" value="" required>
                </div>
                <div class="mb-3">
                    <textarea name="userMsg" class="form-control" placeholder="MESSAGE" style="width: 100%; height: 150px;"></textarea>
                </div>
                <div class="mt-3">
                    <input type="file" class="form-control" value="Browse" name="avatar" id="cvFile" />
                </div>
                 <div class="mt-3">
                    <input type="submit" name="Submit" class="btn btn-circle" value="Submit">
                </div>
            </div>
          </div>
        </form>
      </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'career-slice'
}
</script>

<style>
.form-control,.form-select {
  border:1px solid #5b146f;
}
.btn-circle {
  color: #5b146f;
  border:2px solid #5b146f;
  border-radius: 48px;
  padding: 10px 100px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #5b146f;
}
</style>