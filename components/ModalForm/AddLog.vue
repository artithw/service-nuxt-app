<template>
  <div class="modal-card" style="width: 840" full-screen>
    <header class="modal-card-head">
      <p class="modal-card-title">บันทึกงาน</p>
    </header>
    <section class="modal-card-body">
      <b-field label="เรื่อง">
        <b-input></b-input>
      </b-field>
      <b-field label="รายละเอียด">
        <b-input maxlength="200" type="textarea"></b-input>
      </b-field>
      <b-field label="ผู้รับบริการ">
        <b-input></b-input>
      </b-field>
      <b-field label="สังกัด">
        <b-select v-model="institute" placeholder="institute" required>
          <option value="สำนักงานวิทยาเขต">สำนักงานวิทยาเขต</option>
          <option value="คณะครุศาสตร์อุตสาหกรรม">คณะครุศาสตร์อุตสาหกรรม</option>
          <option value="คณะวิศวกรรมศาตร์">คณะวิศวกรรมศาตร์</option>
          <option value="คณะบริหารธุรกิจและเทคโนโลยีสารสนเทศ">
            คณะบริหารธุรกิจและเทคโนโลยีสารสนเทศ
          </option>
        </b-select>
      </b-field>
      <b-field label="แผนก">
        <b-select
          v-model="department"
          placeholder="Select a department"
          required
        >
          <option value="กองทุน">กองทุน</option>
          <option value="เบิกจ่าย">เบิกจ่าย</option>
          <option value="การเงิน">การเงิน</option>
          <option value="พัสดุ">พัสดุ</option>
          <option value="ทะเบียน">ทะเบียน</option>
          <option value="เลขา">เลขา</option>
        </b-select>
      </b-field>
      <b-field label="ผู้ให้บริการ">
        <b-input></b-input>
      </b-field>
      <b-field label="รายละเอียด">
        <b-input maxlength="200" type="textarea"></b-input>
      </b-field>
      <b-field label="สถานะ">
        <b-select v-model="status" placeholder="Select a status" required>
          <option value="เรียบร้อย">เรียบร้อย</option>
          <option value="รออุปกรณ์">รออุปกรณ์</option>
          <option value="แก้ไขไม่ได้">แก้ไขไม่ได้</option>
        </b-select>
      </b-field>
    </section>
    <footer class="modal-card-foot">
      <button class="button" type="button" @click="$parent.close()">
        Close
      </button>
      <button class="button is-info">บันทึก</button>
    </footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isComponentModalActive: false,
      email: 'evan@you.com',
      password: 'testing',
      status: ['เรียบร้อย', 'รออุปกรณ์', 'แก้ไขไม่ได้'],
      department: ['กองทุน', 'เบิกจ่าย', 'การเงิน', 'พัสดุ', 'ทะเบียน', 'เลขา'],
      institute: [
        'สำนักงานวิทยาเขต',
        'คณะครุศาสตร์อุตสาหกรรม',
        'คณะวิศวกรรมศาตร์',
        'คณะบริหารธุรกิจและเทคโนโลยีสารสนเทศ',
      ],
    }
  },
}
</script>
