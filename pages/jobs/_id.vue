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
              <select v-model="jobs.data.institute">
                <option value="สำนักงานวิทยาเขต">สำนักงานวิทยาเขต</option>
                <option value="คณะครุศาสตร์อุตสาหกรรม">
                  คณะครุศาสตร์อุตสาหกรรม
                </option>
                <option value="คณะวิศวกรรมศาตร์">คณะวิศวกรรมศาตร์</option>
                <option value="คณะบริหารธุรกิจและเทคโนโลยีสารสนเทศ">
                  คณะบริหารธุรกิจและเทคโนโลยีสารสนเทศ
                </option>
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
              <select v-model="jobs.data.department">
                <option value="กองทุน">กองทุน</option>
                <option value="เบิกจ่าย">เบิกจ่าย</option>
                <option value="การเงิน">การเงิน</option>
                <option value="พัสดุ">พัสดุ</option>
                <option value="ทะเบียน">ทะเบียน</option>
                <option value="เลขา">เลขา</option>
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
              v-model="jobs.data.fixdetail"
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
              <select v-model="jobs.data.fixstatus">
                <option value="เรียบร้อย">เรียบร้อย</option>
                <option value="รออุปกรณ์">รออุปกรณ์</option>
                <option value="แก้ไขไม่ได้">แก้ไขไม่ได้</option>
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
            <button class="button is-primary">
              บันทึก {{ $route.params.id }}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  async asyncData({ $axios, params }) {
    const jobs = await $axios.$get(
      // eslint-disable-next-line
      `http://localhost:3030/api/fixlog/${params.id}`
    )
    // eslint-disable-next-line
    console.log(params.id)
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
    }
  },
  head() {
    return {
      title: 'บันทึกรายละเอียดการให้บริการ',
    }
  },
}
</script>
