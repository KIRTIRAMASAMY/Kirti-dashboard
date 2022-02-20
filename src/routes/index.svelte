<script>
 import supabase from "$lib/db";

  function addTimeSlot(day){
if (day==="Monday") {
	timetable.Monday = [
    ...timetable.Monday,
    { name: "??", period: 1, style: "" }
  ];

   else if (day==="Tuesday") {
	timetable.Tuesday = [
    ...timetable.Tuesday,
    { name: "??", period: 1, style: "" }
  ];

  else if (day==="Wednesday") {
	timetable.Wednesday = [
    ...timetable.Wednesday,
    { name: "??", period: 1, style: "" }
  ];

  else if (day==="Thursday") {
	timetable.Thursday = [
    ...timetable.Thursdayday,
    { name: "??", period: 1, style: "" }
  ];

  else if (day==="Friday") {
	timetable.Friday = [
    ...timetable.Friday,
    { name: "??", period: 1, style: "" }
  ];
}
  }


  let timetable = {
	Monday: [
  	{
    	name: "PH",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BI",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "R",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
	],
	Tuesday: [
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BI",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "E",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
	],
	Wednesday: [
  	{
    	name: "BC",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "H",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "PKS",
    	period: 3,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
	],
	Thursday: [
  	{
    	name: "SA",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "PJPK",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "A",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "M3",
    	period: 2,
    	style: "",
  	},
	],
	Friday: [
  	{
    	name: "BI",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "BM",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "T",
    	period: 1,
    	style: "table-success",
  	},
  	{
    	name: "BC",
    	period: 2,
    	style: "",
  	},
  	{
    	name: "PM",
    	period: 1,
    	style: "",
  	},
  	{
    	name: "SA",
    	period: 2,
    	style: "",
  	},
	],
  };



</script>

<div class="container mt-5">
<h1><b><u>My Dashboard</u></b></h1>
<br>
<caption> School Timetable </caption>
<br>
<table class="table">
    <thead>
      <tr class="table-dark">
        <th scope="col">Day</th>
        <th scope="col">1</th>
        <th scope="col">2</th>
        <th scope="col">3</th>
        <th scope="col">4</th>
        <th scope="col"> </th>
        <th scope="col">5</th>
        <th scope="col">6</th>
        <th scope="col">7</th>
        <th scope="col">8</th>
        <th scope="col">9</th>
        <th scope="col">10</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row" class="table-dark" >Mon</th>
        {#each timetable.Monday as timeSlot, index}
      	<td colspan={timeSlot.period} class={timeSlot.style}>
        	<button
          	type="button"
          	class="btn"
        	>
          	{timeSlot.name}
        	</button>
      	</td>
    	{/each}
		<td>
			<button on:click={() => addTimeSlot("Monday")} class="btn">+</button>
			</td>

      <tr>
        <th scope="row" class="table-dark">Tue</th>
        {#each timetable.Tuesday as timeSlot, index}
      	<td colspan={timeSlot.period} class={timeSlot.style}>
        	<button
          	type="button"
          	class="btn"
        	>
          	{timeSlot.name}
        	</button>
      	</td>
    	{/each}
		<td>
			<button on:click={() => addTimeSlot("Tuesday")} class="btn">+</button>
			</td>
      </tr>
      <tr>
        <th scope="row" class="table-dark">Wed</th>
        {#each timetable.Wednesday as timeSlot, index}
      	<td colspan={timeSlot.period} class={timeSlot.style}>
        	<button
          	type="button"
          	class="btn"
        	>
          	{timeSlot.name}
        	</button>
      	</td>
    	{/each}
		<td><button on:click={() => addTimeSlot("Wednesday")} class="btn">+</button>
			</td>
      </tr>
      <tr>
        <th scope="row" class="table-dark">Thrs</th>
        {#each timetable.Thursday as timeSlot, index}
      	<td colspan={timeSlot.period} class={timeSlot.style}>
        	<button
          	type="button"
          	class="btn"
        	>
          	{timeSlot.name}
        	</button>
      	</td>
    	{/each}
		<td>
			<button on:click={() => addTimeSlot("Thursday")} class="btn">+</button>
			</td>
      </tr>
      <tr>
        <th scope="row" class="table-dark">Fri</th>
        {#each timetable.Friday as timeSlot, index}
      	<td colspan={timeSlot.period} class={timeSlot.style}>
        	<button
          	type="button"
          	class="btn"
        	>
          	{timeSlot.name}
        	</button>
      	</td>
    	{/each}
		<td>
			<button on:click={() => addTimeSlot("Friday")} class="btn">+</button>
			</td>
      </tr>
    </tbody>
  </table>

</div>

  <!-- Sign Out -->
<div class="text-center mt-5">
  <button class="btn btn-secondary" on:click={logout}>Logout</button>
</div>


