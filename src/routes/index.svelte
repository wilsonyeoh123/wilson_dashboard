<script>

    import supabase from '$lib/db';
import { bind, bubble } from 'svelte/internal';

    async function logout() {
   	 const { error } = await supabase.auth.signOut();

   	 if (error) alert(error.message); // alert if error
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

  function addTimeSlot(day){
	  if(day ==="Monday"){
		timetable.Monday = [
    ...timetable.Monday,
    { name: "??", period: 1, style: "" }
	 ];
	  }else if (day === "Tuesday"){
	  timetable.Tuesday = [
    ...timetable.Tuesday,
    { name: "??", period: 1, style: "" }
  ];
	  }else if (day === "Wednesday"){
		timetable.Wednesday = [
    ...timetable.Wednesday,
    { name: "??", period: 1, style: "" }
  ];
	  }else if (day === "Thursday"){
		timetable.Thursday = [
    ...timetable.Thursday,
    { name: "??", period: 1, style: "" }
  ];
	  }else if (day === "Friday"){
		timetable.Friday = [
    ...timetable.Friday,
    { name: "??", period: 1, style: "" }
  ];
  }
 };

  let curDay;
  let curIndex;
  let curName;
  let curPeriod;
  let curStyle;

  function showCurData(day, index, name, period, style){
	  curDay = day;
	  curIndex = index;
	  curName = name;
	  curPeriod = period;
	  curStyle = style;
  }
   function  deleteTimeSlot(day,index){
   if (day === "Monday") {
  	timetable.Monday[index].name = newName;
  	timetable.Monday[index].period = newPeriod;
  	timetable.Monday[index].style = newStyle;
	}
	if (day === "Tueday") {
  	timetable.Monday[index].name = newName;
  	timetable.Monday[index].period = newPeriod;
  	timetable.Monday[index].style = newStyle;
	}
	if (day === "Wednesday") {
  	timetable.Monday[index].name = newName;
  	timetable.Monday[index].period = newPeriod;
  	timetable.Monday[index].style = newStyle;
	}
	if (day === "Thursday") {
  	timetable.Monday[index].name = newName;
  	timetable.Monday[index].period = newPeriod;
  	timetable.Monday[index].style = newStyle;
	}
	if (day === "Friday") {
  	timetable.Monday[index].name = newName;
  	timetable.Monday[index].period = newPeriod;
  	timetable.Monday[index].style = newStyle;
	}
}

</script>
<div class="container">
    <h1>my dashboard</h1>
    <caption>TIMETABLE</caption>
        
    <table class="table  table-striped text-center table-bordered">
        <thead class="table-dark">
          <tr>
            <th scope="col">#</th>
            <th scope="col">1</th>
            <th scope="col">2</th>
            <th scope="col">3</th>
            <th scope="col">4</th>
            <th scope="col">-</th>
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
            <th scope="row" class="table-dark">Monday</th>
            {#each timetable.Monday  as timeSlot,index}
                <td colspan={timeSlot.period} class={timeSlot.style}>
                <button type="button" class="btn" data-bs-toggle="modal" data-bs-target="#EditModal" on:click={() =>
					showCurData(
					  "Monday",
					  index,
					  timeSlot.name,
					  timeSlot.period,
					  timeSlot.style
					)}
		>
                    {timeSlot.name}
                </button>
                </td>
            {/each}
			<td>
				<button class="btn" 
				on:click={() => addTimeSlot("Monday")}>+</button>
			</td>
          </tr>
          <tr>
            <th scope="row"class="table-dark">Tuesday</th>
            {#each timetable.Tuesday  as timeSlot,index}
                <td colspan={timeSlot.period} class={timeSlot.style}>
                <button type="button" class="btn"data-bs-toggle="modal" data-bs-target="#EditModal" on:click={() =>
					showCurData(
					  "Tuesday",
					  index,
					  timeSlot.name,
					  timeSlot.period,
					  timeSlot.style
					)}>
                    {timeSlot.name}
                </button>
                </td>
            {/each}
          </tr>
          <tr>
            <th scope="row"class="table-dark">Wednesday</th>
            {#each timetable.Wednesday  as timeSlot,index}
                <td colspan={timeSlot.period} class={timeSlot.style}>
                <button type="button" class="btn" data-bs-toggle="modal" data-bs-target="#EditModal" on:click={() =>
					showCurData(
					  "Wednesday",
					  index,
					  timeSlot.name,
					  timeSlot.period,
					  timeSlot.style
					)}>
                    {timeSlot.name}
                </button>
                </td>
            {/each}
          </tr>
          <tr>
            <th scope="row"class="table-dark">Thursday</th>
            {#each timetable.Thursday  as timeSlot,index}
                <td colspan={timeSlot.period} class={timeSlot.style}>
                <button type="button" class="btn" data-bs-toggle="modal" data-bs-target="#EditModal" on:click={() =>
					showCurData(
					  "Thursday",
					  index,
					  timeSlot.name,
					  timeSlot.period,
					  timeSlot.style
					)}>
                    {timeSlot.name}
                </button>
                </td>
            {/each}
          </tr>
          <tr>
            <th scope="row"class="table-dark">Friday</th>
            {#each timetable.Friday  as timeSlot,index}
                <td colspan={timeSlot.period} class={timeSlot.style}>
                <button type="button" class="btn" data-bs-toggle="modal" data-bs-target="#EditModal" on:click={() =>
					showCurData(
					  "Friday",
					  index,
					  timeSlot.name,
					  timeSlot.period,
					  timeSlot.style
					)}>
                    {timeSlot.name}
                </button>
                </td>
            {/each}
          </tr>
        </tbody>
      </table>
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
	Launch demo modal
  </button>
  
  <!-- Modal -->
  <div class="modal fade" id="EditModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
	<div class="modal-dialog">
	  <div class="modal-content">
		<div class="modal-header">
		  <h5 class="modal-title" id="EditModal">Edit Time Slot</h5>
		  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
		</div>
		<div class="modal-body">
			<div class="input-group mb-3">
				<span class="input-group-text" id="name">name</span>
				<input type="text" class="form-control" bind:value={curName}>
			  </div>
			  <div class="input-group mb-3">
				<span class="input-group-text" id="period">period</span>
				<input type="text" class="form-control" bind:value={curPeriod}>
			  </div>
			  <div class="input-group mb-3">
				<label class="input-group-text" for="inputGroupSelect01">Options</label>
				<select class="form-select" id="inputGroupSelect01" bind:value={curStyle}>
				  <option value="">default</option>
				  <option value="table-primary">blue</option>
				  <option value="table-success">green</option>
				  <option value="table-danger">red</option>				
				  <option value="table-warning">yellow</option>
				  <option value="table-secondary">grey</option>
				</select>
			  </div>
		</div>
		<div class="modal-footer">
		  <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Cancle</button>
		  <button type="button" class="btn btn-primary" on:click={deleteTimeSlot}>Delete</button>
		  <button type="button" class="btn btn-primary">Save changes</button>
		</div>
		</div>
	  </div>
	</div>
  </div>
<!-- Sign Out -->
<section class="container px-4 py-3 text-center">
    <button class="btn btn-secondary" on:click={logout}>Logout</button>
</section>		



