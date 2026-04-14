<template>
  <section class="bg-white py-60">
    <div class="container mx-auto px-4">
      <div class="max-w-2xl mx-auto mb-16 text-center">
        <div
          class="text-lg uppercase tracking-widest text-[#3ea8db] font-medium mb-2"
        >
          Get In Touch
        </div>
        <h2 class="text-4xl md:text-5xl font-light text-gray-900 leading-tight">
          Contact Us
        </h2>
        <p class="mt-4 text-gray-600 leading-relaxed">
          Feel free to call or message us. We're here to help with your glazing
          needs.
        </p>
      </div>

      <div class="max-w-xl mx-auto space-y-8 lg:flex justify-between mb-12">
        <div class="flex items-start gap-4">
          <div
            class="flex-shrink-0 w-12 h-12 bg-[#3ea8db] bg-opacity-10 rounded-xl flex items-center justify-center"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 text-white"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M14.25 9.75v-4.5m0 4.5h4.5m-4.5 0 6-6m-3 18c-8.284 0-15-6.716-15-15V4.5A2.25 2.25 0 0 1 4.5 2.25h1.372c.516 0 .966.351 1.091.852l1.106 4.423c.11.44-.054.902-.417 1.173l-1.293.97a1.062 1.062 0 0 0-.38 1.21 12.035 12.035 0 0 0 7.143 7.143c.441.162.928-.004 1.21-.38l.97-1.293a1.125 1.125 0 0 1 1.173-.417l4.423 1.106c.5.125.852.575.852 1.091V19.5a2.25 2.25 0 0 1-2.25 2.25h-2.25Z"
              />
            </svg>
          </div>
          <div>
            <h3 class="font-semibold text-gray-900 mb-1">Phone</h3>
            <p class="text-gray-600">+44 7510 429380</p>
            <p class="text-sm text-gray-500 mt-1">
              Mon-Fri 8am-6pm, Sat 9am-4pm
            </p>
          </div>
        </div>

        <div class="flex items-start gap-4">
          <div
            class="flex-shrink-0 w-12 h-12 bg-[#3ea8db] bg-opacity-10 rounded-xl flex items-center justify-center"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 text-white"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
              />
            </svg>
          </div>
          <div>
            <h3 class="font-semibold text-gray-900 mb-1">Email</h3>
            <p class="text-gray-600">info@myglass.co.uk</p>
            <p class="text-sm text-gray-500 mt-1">
              We'll respond within 24 hours
            </p>
          </div>
        </div>
      </div>

      <div
        class="max-w-4xl mx-auto bg-gray-50 rounded-2xl p-8 shadow-lg border border-gray-200"
      >
        <h3 class="text-xl font-semibold text-gray-900 mb-6">
          Send us a message
        </h3>
        <form
          action="https://api.web3forms.com/submit"
          method="POST"
          class="space-y-5"
        >
          <input
            type="hidden"
            name="access_key"
            value="a6747093-e74a-4501-a0de-442b0a2fe9db"
          />
          <input
            type="hidden"
            name="subject"
            value="New Contact Form Submission"
          />
          <div>
            <label
              for="name"
              class="block text-sm font-medium text-gray-700 mb-2"
              >Name</label
            >
            <input
              id="name"
              name="name"
              type="text"
              required
              class="w-full px-4 py-3 bg-white border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#3ea8db] focus:border-transparent outline-none transition-all"
              placeholder="Your name"
            />
          </div>
          <div>
            <label
              for="email"
              class="block text-sm font-medium text-gray-700 mb-2"
              >Email</label
            >
            <input
              id="email"
              name="email"
              type="email"
              required
              class="w-full px-4 py-3 bg-white border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#3ea8db] focus:border-transparent outline-none transition-all"
              placeholder="your.email@example.com"
            />
          </div>
          <div>
            <label
              for="phone"
              class="block text-sm font-medium text-gray-700 mb-2"
              >Phone</label
            >
            <input
              id="phone"
              name="phone"
              type="tel"
              class="w-full px-4 py-3 bg-white border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#3ea8db] focus:border-transparent outline-none transition-all"
              placeholder="+44 1234 567 890"
            />
          </div>
          <div>
            <label
              for="message"
              class="block text-sm font-medium text-gray-700 mb-2"
              >Message</label
            >
            <textarea
              id="message"
              name="message"
              required
              rows="4"
              class="w-full px-4 py-3 bg-white border border-gray-300 rounded-lg focus:ring-2 focus:ring-[#3ea8db] focus:border-transparent outline-none transition-all resize-none"
              placeholder="Tell us about your project..."
            ></textarea>
          </div>
          <button
            type="submit"
            class="w-full bg-[#3ea8db] hover:bg-[#3498c9] text-white font-medium py-3 px-6 rounded-lg transition-colors duration-200"
          >
            Send Message
          </button>
        </form>
      </div>
    </div>
  </section>
</template>
