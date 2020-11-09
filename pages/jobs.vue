<template>
  <section class="section">
    <div class="columns">
      <div class="column">
        <h1 class="title">บันทึกงาน</h1>
        <h2 class="subtitle">บันทึกรายละเอียดการให้บริการ</h2>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">เรื่อง</label>
      </div>
      <div class="field-body">
        <div class="field">
          <p class="control is-expanded">
            <input v-model="jobs.data.title" class="input" type="text" />
            <span class="icon is-small is-left">
              <i class="fas fa-user"></i>
            </span>
          </p>
        </div>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">รายละเอียด</label>
      </div>
      <div class="field-body">
        <div class="field">
          <div class="control">
            <textarea
              v-model="jobs.data.description"
              class="textarea"
              placeholder="รายละเอียด ปัญหา"
            ></textarea>
          </div>
        </div>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">ผู้รับบริการ</label>
      </div>
      <div class="field-body">
        <div class="field">
          <p class="control is-expanded">
            <input
              v-model="jobs.data.names"
              class="input"
              type="text"
              placeholder="username"
            />
            <span class="icon is-small is-left">
              <i class="fas fa-user"></i>
            </span>
          </p>
        </div>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">สังกัด</label>
      </div>
      <div class="field-body">
        <div class="field is-narrow">
          <div class="control">
            <div class="select is-fullwidth">
              <select>
                <option>สำนักงานวิทยาเขต</option>
                <option>คณะครุศาสตร์อุตสาหกรรม</option>
                <option>คณะวิศวกรรมศาตร์</option>
                <option>คณะบริหารธุรกิจและเทคโนโลยีสารสนเทศ</option>
              </select>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">แผนก</label>
      </div>
      <div class="field-body">
        <div class="field is-narrow">
          <div class="control">
            <div class="select is-fullwidth">
              <select>
                <option>กองทุน</option>
                <option>เบิกจ่าย</option>
                <option>การเงิน</option>
                <option>พัสดุ</option>
                <option>ทะเบียน</option>
                <option>เลขา</option>
              </select>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">ผู้ให้บริการ</label>
      </div>
      <div class="field-body">
        <div class="field">
          <p class="control is-expanded">
            <input
              v-model="jobs.data.agent"
              class="input"
              type="text"
              placeholder="เจ้าหน้าที่"
            />
            <span class="icon is-small is-left">
              <i class="fas fa-user"></i>
            </span>
          </p>
        </div>
      </div>
    </div>
    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">รายละเอียด</label>
      </div>
      <div class="field-body">
        <div class="field">
          <div class="control">
            <textarea
              v-model="status.name"
              class="textarea"
              placeholder="รายละเอียด การแก้ไข"
            ></textarea>
          </div>
        </div>
      </div>
    </div>

    <div class="field is-horizontal">
      <div class="field-label is-normal">
        <label class="label">สถานะ</label>
      </div>
      <div class="field-body">
        <div class="field is-narrow">
          <div class="control">
            <div class="select is-fullwidth">
              <select>
                <option>เรียบร้อย</option>
                <option>รออุปกรณ์</option>
                <option>แก้ไขไม่ได้</option>
              </select>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="field is-horizontal">
      <div class="field-label">
        <!-- Left empty for spacing -->
      </div>
      <div class="field-body">
        <div class="field">
          <div class="control">
            <button class="button is-primary">บันทึก</button>
          </div>
          <div>test: {{ status[0] }}</div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const jobs = await $axios.$get('http://localhost:3030/api/fixlog/1')
    // eslint-disable-next-line
    //console.log(jobs.data)
    return { jobs }
  },
  data() {
    return {
      jobs: {},
      // status: [
      //   { id: 1, name: 'เรียบร้อย' },
      //   { id: 2, name: 'รออุปกรณ์' },
      //   { id: 3, name: 'แก้ไขไม่ได้' },
      // ],
      status: ['เรียบร้อย', 'รออุปกรณ์', 'แก้ไขไม่ได้'],
    }
  },
  head() {
    return {
      title: 'บันทึกรายละเอียดการให้บริการ',
    }
  },
}
</script>
