
To obtain query code > navigate to https://app.roqs.basf.net/hub_services_db

Log-in on hub_sevices_DB > open the console > look for  [Auth Middleware nuxt3]: Query code is  "5f16fc43ff1dd99a44bdbf5e33d3f76a2a91e8781e19972a875578852df6622f" or similar, replace this in the url for "query_code"

Make sure the back-end is running VS Code > navigate to the back-end > cd express

Run "npm run watch", the first time then "npm run dev"

Make sure the front end is running cd nuxt > "npm run dev"

Open a browser and navigate to http://localhost:3000/?code="query_code"




  <tr

    class="border-b transition-colors hover:bg-darkBlue/10 hover:cursor-pointer data-[state=selected]:bg-muted odd:bg-muted/50 w-full"

    data-state="false"

  >

    <td

      class="p-2 px-6 text-center w-1/5"

    >

      <div class="flex items-center justify-center w-full h-full">Headhunter</div>

    </td>

    <td

      class="p-2 px-6 text-center w-1/5"

    >

      <div class="flex items-center justify-center w-full h-full">headhunter info 1</div>

    </td>

    <td

      class="p-2 px-6 text-center w-1/5"

    >

      <div class="flex items-center justify-center w-full h-full">de</div>

    </td>

    <td

      class="p-2 px-6 text-center w-1/5"

    >

      <div class="flex items-center justify-center w-full h-full">text</div>

    </td>

    <td

      class="p-2 px-6 text-center w-1/5"

    >

      <div class="flex items-center justify-center space-x-2 bg-red-500">

        <button class="p-1 rounded-full hover:bg-gray-200">

          <svg

            xmlns="http://www.w3.org/2000/svg"

            width="24"

            height="24"

            viewBox="0 0 24 24"

            fill="none"

            stroke="currentColor"

            stroke-width="2"

            stroke-linecap="round"

            stroke-linejoin="round"

            class="lucide lucide-pencil-icon h-4 w-4"

          >

            <path

              d="M21.174 6.812a1 1 0 0 0-3.986-3.987L3.842 16.174a2 2 0 0 0-.5.83l-1.321 4.352a.5.5 0 0 0 .623.622l4.353-1.32a2 2 0 0 0 .83-.497z"

            ></path>

            <path d="m15 5 4 4"></path>

          </svg>

        </button>

        <button class="p-1 rounded-full hover:bg-gray-200">

          <svg

            xmlns="http://www.w3.org/2000/svg"

            width="24"

            height="24"

            viewBox="0 0 24 24"

            fill="none"

            stroke="currentColor"

            stroke-width="2"

            stroke-linecap="round"

            stroke-linejoin="round"

            class="lucide lucide-trash2-icon h-4 w-4"

          >

            <path d="M3 6h18"></path>

            <path

              d="M19 6v14c0 1-1 2-2 2H7c-1 0-2-1-2-2V6"

            ></path>

            <path d="M8 6V4c0-1 1-2 2-2h4c1 0 2 1 2 2v2"></path>

            <line x1="10" x2="10" y1="11" y2="17"></line>

            <line x1="14" x2="14" y1="11" y2="17"></line>

          </svg>

        </button>

      </div>

    </td>

  </tr>

