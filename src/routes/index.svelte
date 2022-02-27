<script>
 import supabase from "$lib/db";
 

 let curDay ;
 let curIndex ;
 let curName ;
 let curPeriod ;
 let curStyle ;

 function showCurData(day,index,name,period,style){
	curDay = day
	curIndex = index
	curName = name
	curPeriod = period
	curStyle = style

 }

  function addTimeSlot(day){
if (day==="Monday") {
	timetable.Monday = [
    ...timetable.Monday,
    { name: "??", period: 1, style: "" }
  ];
}
   else if (day==="Tuesday") {
	timetable.Tuesday = [
    ...timetable.Tuesday,
    { name: "??", period: 1, style: "" }
  ];
   }
  else if (day==="Wednesday") {
	timetable.Wednesday = [
    ...timetable.Wednesday,
    { name: "??", period: 1, style: "" }
  ];
  }
  else if (day==="Thursday") {
	timetable.Thursday = [
    ...timetable.Thursdayday,
    { name: "??", period: 1, style: "" }
  ];
  }
  else if (day==="Friday") {
	timetable.Friday = [
    ...timetable.Friday,
    { name: "??", period: 1, style: "" }
  ];
}
  }

  function deleteTimeSlot(day,index){
	 timetable[day].splice(index,1);
	 timetable=timetable;
  }

  function setTimeSlot(day,index,newName,newPeriod,newStyle){
	  timetable [day] [index] . name = newName ;
	  timetable [day] [index] . period = newPeriod ;
	  timetable [day] [index] . style = newStyle ;
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

  async function logout() {
    const { error } = await supabase.auth.signOut();

    if (error) alert(error.message); // alert if error
  }


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
        {#each timetable.Monday as timeSlot, index }
      	<td colspan={timeSlot.period} class={timeSlot.style}>
        	<button
          	type="button"
          	class="btn" data-bs-toggle="modal"  data-bs-target="#editTimeSlot" 
			  on:click={()=>showCurData("Monday",index,timeSlot.name,timeSlot.period,timeSlot.style)}
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
          	class="btn" data-bs-toggle="modal"  data-bs-target="#editTimeSlot" 
			  on:click={()=>showCurData("Tuesday",index,timeSlot.name,timeSlot.period,timeSlot.style)}
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
          	class="btn" data-bs-toggle="modal"  data-bs-target="#editTimeSlot" 
			  on:click={()=>showCurData("Wednesday",index,timeSlot.name,timeSlot.period,timeSlot.style)}
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
          	class="btn" data-bs-toggle="modal"  data-bs-target="#editTimeSlot" 
			  on:click={()=>showCurData("Thursday",index,timeSlot.name,timeSlot.period,timeSlot.style)}
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
          	class="btn" data-bs-toggle="modal"  data-bs-target="#editTimeSlot" 
			  on:click={()=>showCurData("Friday",index,timeSlot.name,timeSlot.period,timeSlot.style)}
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


<!-- Modal -->
<div class="modal fade" id="editTimeSlot" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Edit Time Slot</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
		<div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon1">Name</span>
  <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1"
  bind:value={curName}  >
</div>

<div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon1">Period</span>
  <input type="number" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1"
  bind:value={curPeriod}>
</div>

      
		<div class="input-group mb-3">
			<label class="input-group-text" for="styleSelect">Period</label>
  <select class="form-select" id="styleSelect" bind:value={curStyle}>
    <option selected value="">Default</option>
    <option value="table-primary">Blue</option>
    <option value="table-success">Green</option>
    <option value="table-danger">Red</option>
	<option value="table-secondary">Grey</option>
	<option value="table-warning">Yellow</option>
  </select>
</div>

</div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
        <button type="button" class="btn btn-danger" data-bs-dismiss="modal" on:click={()=>deleteTimeSlot(curDay,curIndex,curName,curPeriod,curStyle)}></button>
		<button type="button" class="btn btn-primary">Save Changes</button>
		 on:click={()=>setTimeSlot(curDay,curIndex,curName,curPeriod,curStyle)}
      </div>
    </div>
  </div>
</div>

  <!-- Sign Out -->
<div class="text-center mt-5">
  <button class="btn btn-secondary" on:click={logout}>Logout</button>
</div>


