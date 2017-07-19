# zj
import { DatePicker } from 'antd';
import moment from 'moment';
const { MonthPicker, RangePicker } = DatePicker;

const dateFormat = 'YYYY/MM/DD';
const monthFormat = 'YYYY/MM';
ReactDOM.render(
  <div>
    <DatePicker defaultValue={moment('2017/07/19', dateFormat)} format={dateFormat} />
    <br />
    <MonthPicker defaultValue={moment('2017/07', monthFormat)} format={monthFormat} />
    <br />
    <RangePicker
      defaultValue={[moment('2017/07/19', dateFormat), moment('2017/08/31', dateFormat)]}
      format={dateFormat}
    />
  </div>
, mountNode);

import { DatePicker } from 'antd';
const { RangePicker } = DatePicker;

function onChange(value, dateString) {
  console.log('Selected Time: ', value);
  console.log('Formatted Selected Time: ', dateString);
}

function onOk(value) {
  console.log('onOk: ', value);
}

ReactDOM.render(
  <div>
    <DatePicker
      showTime
      format="YYYY-MM-DD HH:mm:ss"
      placeholder="Select Time"
      onChange={onChange}
      onOk={onOk}
    />
    <br />
    <RangePicker
      showTime={{ format: 'HH:mm' }}
      format="YYYY-MM-DD HH:mm"
      placeholder={['Start Time', 'End Time']}
      onChange={onChange}
      onOk={onOk}
    />
  </div>
, mountNode);
