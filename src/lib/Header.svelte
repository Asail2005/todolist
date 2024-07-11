<script lang="ts">
	import dayjs from 'dayjs';
	import 'dayjs/locale/ar';
    import{
        ListBox,
        ListBoxItem,
        popup,
        type PopupSettings,
    }from "@skeletonlabs/skeleton";

	dayjs.locale('ar');

	let period = dayjs().format('a') == 'م' ? 'مساء' : " صباح" ;


   
let comboboxValue: string ='مهام اليوم';

const popupCombobox: PopupSettings = {
	event: 'click',
	target: 'popupCombobox',
	placement: 'bottom',
	closeQuery: '.listbox-item'
};
				
		
</script>

<header class="flex justify-between">
    <div>
       <h1 class="text-4xl mb-2r ">{period} الخير👋🏼  </h1>
       <h2 class="text-2xl text-slate-400">
    {dayjs().format('اليوم , dddd D MMM YYYY')}
    </h2>
    </div>

    
<button 

    class="btn variant-soft-surface text-2xl w-48 h-fit py-4 justify-between"
	 use:popup={popupCombobox}>
	<span >{comboboxValue }</span>
	<span class="!m-0">
		<svg class="w-6" xmlns="http://www.w3.org/2000/svg"
		 viewBox="0 0 
		 24 24"><path fill="currentColor" fill-rule
		 ="evenodd" d="m6 7l6 6l6-6l2 2l-8 8l-8-8z
		 "/></svg>
	</span>

</button>
				

<div class="card w-48 shadow-xl py-2 " data-popup="popupCombobox">
	<ListBox rounded="rounded-none" active="bg-indigo-300/15">
		<ListBoxItem bind:group={comboboxValue} name="medium" value="جميع المهام">جميع المهام</ListBoxItem>
		<ListBoxItem bind:group={comboboxValue} name="medium" value="مهام اليوم">مهام اليوم</ListBoxItem>
	</ListBox>
	<div class="arrow bg-surface-100-800-token" />
</div>
					
	

</header>