<template>
  <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
      <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 col-sm-12 mx-auto text-center">
        <form method="post">
          <div class="row">
            <div class="col-md-6">
                <div class="mb-3">
                    <input type="text" name="userName" class="form-control" placeholder="NAME" value="" required>
                </div>
                <select class="form-select mb-3" aria-label="Default select example">
                  <option selected>I'M A</option>
                  <option value="1">One</option>
                  <option value="2">Two</option>
                  <option value="3">Three</option>
                </select>
                <div class="mb-3">
                    <input type="text" name="userPhone" class="form-control" placeholder="TELEPHONE" value="" required>
                </div>
            </div>
            <div class="col-md-6 text-md-start">
                <div class="mb-3">
                    <input type="text" name="userEmail" class="form-control" placeholder="EMAIL" value="" required>
                </div>
                <div class="mb-3">
                    <input type="text" name="userCompany" class="form-control" placeholder="COMPANY (IF APPLICABLE)" value="">
                </div>
                <div class="mb-3">
                    <textarea name="userMsg" class="form-control" placeholder="MESSAGE" style="width: 100%; height: 150px;"></textarea>
                </div>
                <div class="mt-3">
                    <input type="submit" name="Submit" class="btn btn-circle" value="Submit">
                </div>
                <div class="mt-5">
                     <ul class="list-group list-group-flush text-start m-0 p-0">
                        <li class="list-group-item bg-transparent border-bottom-0 m-0 p-1 fm-pink">Email : <a class="text-decoration-none fm-black" href="mailto:hello@finalmile.io"><em>hello@finalmile.io</em></a></li>
                      </ul>
                </div>
                <div class="mt-4">
                  <ul class="list-group list-group-horizontal m-0 p-0">
                    <a alt="linkedin" target="_blank" rel="noopener" href="https://www.linkedin.com/company/final-mile-kiwi-ventures" class="fm-purple text-decoration-none btn-circle-social">
                      <li class="text-lg-start text-md-start text-mb-start list-group-item bg-transparent border-0 m-0 p-1">
                          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-linkedin" viewBox="0 0 16 16">
                            <path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854V1.146zm4.943 12.248V6.169H2.542v7.225h2.401zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248-.822 0-1.359.54-1.359 1.248 0 .694.521 1.248 1.327 1.248h.016zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016a5.54 5.54 0 0 1 .016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225h2.4z"/>
                          </svg>
                      </li>
                    </a>
                  </ul>
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
  name: 'contact-slice'
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
.btn-circle-social {
  color: #5b146f;
  border:2px solid #5b146f;
  border-radius: 48px;
  padding: 10px 14px;
}
.btn-circle-social:hover {
  color: #fff;
  border:2px solid #fff;
  background: #5b146f;
}
</style>