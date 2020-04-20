<script>
  import moment from 'moment';
  const format = date => moment(date).format('HH:mm:ss');
  let now = new Date();
  let displayTime = format(now);
  setInterval(() => {
    now = new Date();
    displayTime = format(now);
  }, 1000)
</script>

<style>
  time {
    display: block;
    font-family: 'Dank Mono', monospace;
    font-size: 1em;
    text-align: center;
  }
</style>

<time datetime={now}>{displayTime}</time>