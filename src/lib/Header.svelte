<script lang="ts">
	import dayjs from 'dayjs';
	import 'dayjs/locale/ar';

	dayjs.locale('ar');

	let period = dayjs().format('a') == 'م' ? 'مساء' : "صباح";
</script>

<header class="flex justify-between">
    <div>
       <h1 class="text-4xl mb-2r ">{period}الخير 👋🏼 </h1>
       <h2 class="text-2xl text-surface-900/50">
    {dayjs().format('اليوم , dddd D MMM YYYY')}
    </h2>
    </div>
    <div class="bg-red-400 w-32 h-10"> </div>
</header>