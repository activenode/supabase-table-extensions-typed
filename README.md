# Best for JSON-types: A way to extend the Database types beyond the automatic generator

Always running `supabase gen types typescript` but annoyed that it cannot (it really can't because it doesn't know) derive your JSON columns? 
But you do know that your JSON column will always be a certain structure?

Here's the solution: An easy way to adapt the derived types and having fully typed JSON columns within your Supabase client.

## How to use

### The old way

1. You generate the types at `supabase.ts`
1. You `import { Database } from './supabase';`
1. You instantiate a client with `createClient<Database>` from the previous import

### The new way

1. You generate the types at `supabase.ts`
1. You copy the file `supabase.extended.ts` to the same directory
1. You adapt `TableExtensions` to your likings
1. You `import { Database } from './supabase.extended`
1. You instantiate a client with `createClient<Database>` from the previous import (of the extended file, not the `supabase.ts`)

That's it.

