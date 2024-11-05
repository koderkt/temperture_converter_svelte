<script lang="ts">
	

    class  Temperature {
         #celsius: number = $state(0)
         #fahrenhiet: number = $state(0)

         get celsius(){
            return this.#celsius;
         }

         set celsius(celsius){
            this.#celsius = celsius
            this.#fahrenhiet = celsius * (9 / 5) + 32;
         }


         get fahrenhiet(){
            return this.#fahrenhiet;
         }

         set fahrenhiet(fahrenhiet){
            this.#fahrenhiet = fahrenhiet
            this.#celsius = (fahrenhiet - 32) * (5 / 9);
         }
    }
    const  temperature: Temperature = new Temperature();
	// function celsiusToFahrenhiet() {
	// 	fahrenhiet = celsius * (9 / 5) + 32;
	// }    

	// function fahrenhietToCelsius() {
	// 	celsius = (fahrenhiet - 32) * (5 / 9);
	// }
</script>
<div class="flex items-center justify-center h-screen bg-gray-100">
	<div class="bg-white p-16 rounded-lg shadow-md w-full max-w-md">
		<h2 class="text-2xl font-semibold text-gray-700 text-center mb-6">Temperature Converter</h2>
		<div class="flex flex-col gap-4">
			<div class="flex items-center gap-4">
				<input
					type="number"
					bind:value={temperature.celsius}
					class="p-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 w-full"
					placeholder="Enter Celsius"
				/>
				<span class="text-gray-600">°C =</span>
			</div>
			<div class="flex items-center gap-4">
				<input
					type="number"
					bind:value={temperature.fahrenhiet}
					class="p-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 w-full"
					placeholder="Enter Fahrenheit"
				/>
				<span class="text-gray-600">°F</span>
			</div>
		</div>
	</div>
</div>
